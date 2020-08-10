# <center>数字货币内部接口测试版本</center>

## 介绍说明
* 目前只支持数字货币,支持包括ada,bch,btc,eos,etc,eth,link,ltc,neo,trx,xrp在内的11个usdt交易区品种
* 暂时提供两个k线相关的http接口(后续会合并成一个)和一个websocket接口订阅实时k线数据
* 2020-07-31 新增一个数字货币合成实时报价http接口和一个websocket订阅接口
* http base url为 https://api.trochil.cn
* websocket base url为 wss://stream.trochil.cn
* **目前可用测试apikey为 0edbb99e3598972d4c0c81720104test**

## 1. 日线周线月线的历史数据

http接口1,查询日线级别以上历史k线数据,可包括截止到当前时间的最新数据,url中的xxx为市场类型,市场类型包括cnstock,hkstock,usstock,cnfuture,forex,crypto.目前只支持crypto

### GET /v1/kline/xxx/history

请求参数

|参数名|是否必须|类型|描述|默认值|
|:-----  |:-----|-----|:-----  |:-----|
|symbol |Ture   |string |品种代码如btcusdt |无
|startDate |False   |string |k线开始时间 |2020-01-01
|endDate |False   |string |k线结束时间 |当前时间
|timeframe |False   |string |时间频率如日-D,周-W,月-M |D
|apikey |Ture   |string |账户apikey |无

响应参数


|参数名|是否必须|类型|描述|
|:-----  |:-----|-----|:-----  |
|data |Ture   |list |对用品种的k线信息 |
|timestamp |Ture   |int |响应时间 |
|status |Ture   |string |请求结果状态 |   |

data说明

|参数名|是否必须|类型|描述|
|:-----  |:-----|-----|:-----  |
|open |Ture   |float |开盘价 |
|high |Ture   |float |最高价 |
|low |Ture   |float |最低价 |
|close |Ture   |float |收盘价 |
|datetime |Ture   |string |k线时间 |
|timeZone |Ture   |string |k线时区 |

## 2. 日内级别k线数据

http接口2,查询日内k线级别数据,可包括截止到当前时间的最新数据,url中的xxx为市场类型,市场类型包括cnstock,hkstock,usstock,cnfuture,forex,crypto.目前只支持crypto

### GET /v1/kline/xxx/intraday

请求参数

|参数名|是否必须|类型|描述|默认值|
|:-----  |:-----|-----|:-----  |:-----|
|symbol |Ture   |string |品种代码如btcusdt |无
|range |False   |int |获取数据的天数,以结束时间往前range天<br>一分钟数据不超过7天,其他时间不超过30天 |7
|endDate |False   |string |k线结束时间 |当前时间
|timeframe |False   |string |时间频率如分钟级m1,m5,m15,m30,小时级H1,H4 |无
|apikey |Ture   |string |账户apikey |无

响应参数


|参数名|是否必须|类型|描述|
|:-----  |:-----|-----|:-----  |
|data |Ture   |list |对用品种的k线信息 |
|timestamp |Ture   |int |响应时间 |
|status |Ture   |string |请求结果状态 |   |

data说明

|参数名|是否必须|类型|描述|
|:-----  |:-----|-----|:-----  |
|open |Ture   |float |开盘价 |
|high |Ture   |float |最高价 |
|low |Ture   |float |最低价 |
|close |Ture   |float |收盘价 |
|datetime |Ture   |string |k线时间 |
|timeZone |Ture   |string |k线时区 |

## 3. websocket订阅实时k线

websocket订阅k线目前仅支持数字货币,可选频率为m1,m5,m15,m30,H1,H4,D,W

websocket接入地址

wss://stream.trochil.cn/ws/kline/ 后拼接市场类型,如数字货币为**wss://stream.trochil.cn/ws/kline/crypto**

成功建立与Websocket服务器的连接后，需要进行apikey认证,发送如下消息认证apikey:

{'op': 'auth', 'apikey': your apiKey}

apikey认证通过后Websocket客户端发送如下请求以订阅特定主题,支持以列表形式一次性发送多个主题：
**{'op': 'sub', 'topic': topic to sub}** **topic**格式为 timeframe_symbol 如 m1_btcusdt

**例子如下:**
{"op": "sub", "topic": ["m1_btcusdt", "m1_ethusdt"]}

成功订阅后，Websocket客户端将收到确认

之后, **每隔1秒左右**Websocket客户端将收到服务器推送的更新消息

取消订阅
取消订阅的格式如下,取消订阅支持以列表形式一次性取消订阅多个主题：

**{'op': 'unsub', 'topic': topic to unsub}**

取消订阅成功后服务器发送确认信息


### ----------------**2020-07-31分割线**-------------------

11个数字货币品种实时合成报价接口与正式环境的接口相差不大,主要改变如下:
1. http接口正式环境为v1/crypto/quote, 内部使用的合成接口为v2/crypto/quote
2. 正式环境的参数需要带交易所标签如binance.btcusdt,内部合成接口不需要如btcusdt即可
3. 实时合成报价内部接口http和ws都不需要验签,当然为方便减少修改也可以传递过来

## 4. 实时合成报价

查询数字货币实时报价,注意可以不传递apikey

### GET v2/crypto/quote

请求参数

|参数名|是否必须|类型|描述|默认值|
|:-----  |:-----|-----|:-----  |:-----|
|symbol |Ture   |string |品种代码如btcusdt,多品种以逗号分隔 |无

响应参数


|参数名|是否必须|类型|描述|
|:-----  |:-----|-----|:-----  |
|data |Ture   |list |对用品种的k线信息 |
|timestamp |Ture   |int |响应时间 |
|status |Ture   |string |请求结果状态 |   |

data说明

|参数名|是否必须|类型|描述|
|:-----  |:-----|-----|:-----  |
|symbol |Ture   |string |交易对 |
|bid |Ture   |float |最优买价 |
|ask |Ture   |float |最优卖价 |
|bid_qty |Ture   |string |买一数量 |
|ask_qty |Ture   |string |卖一数量 |
|bid_feed |Ture   |string |买一价格来源 |
|ask_feed |Ture   |string |卖一价格来源 |


## 5. websocket订阅实时合成报价

websocket接入地址

wss://stream.trochil.cn/ws/v2/crypto

建立连接后客户端发送如下请求以订阅特定主题,支持以列表形式一次性发送多个主题：
**{'op': 'sub', 'topic': topic to sub}** **topic**例子如btcusdt,不需要加交易所标识

**例子如下:**
{'op': 'sub', 'topic': ['btcusdt']}

成功订阅后，Websocket客户端将收到确认

之后, **每当数据有更新**Websocket客户端将收到服务器推送的更新消息

取消订阅
取消订阅的格式如下,取消订阅支持以列表形式一次性取消订阅多个主题：

**{'op': 'unsub', 'topic': topic to unsub}**

取消订阅成功后服务器发送确认信息
