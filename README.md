\_\_\_\_服务 Server\_\_\_\_
====

### 1. 获取地址

* **请求方法：**   POST  
+ **路径参考：**   "<WEBSIT/IP>:<PORT>/api/transfer_Out/"  

  |参数名称|类型|必填|样例|描述|
  |:---- |:---:|:--:| --:| --:|
  |timestamp  |String |Yes  |"1234554321" |
  |user_id    |String |Yes  |"2020019428" |
  |block      |String |Yes  |"Bitcoin"    |
  |coin_id    |String |Yes  |"BTC"        |
  |order_id   |String |Yes  |"abcd1234"   |
  |type       |String |Yes  |"full"       |
  |from       |String |Yes  |"...from..." |
  |to         |String |Yes  |"...to..."   |
  |amount     |String |Yes  |"100.0"      |
  |\_sign     |String |Yes  |"abcd1234"|

    {
    "code":200,
    "result":{
        "address":"...ADDRESS..."
        }
    }

### 2. 转账
----
+ **请求方法：**   POST  
+ **路径参考：**   "<WEBSIT/IP>:<PORT>/api/transfer_Out/"  
  
|参数名称|类型|必填|样例|描述|
|:---- |:---:|:--:| --:| --:|
|timestamp  |String |Yes  |"1234554321"|
|user_id    |String |Yes  |"2020019428"|
|block      |String |Yes  |"Bitcoin"|
|coin_id    |String |Yes  |"BTC"|
|order_id   |String |Yes  |"abcd1234"|
|type       |String |Yes  |"full"|
|from       |String |Yes  |"....from...."|
|to         |String |Yes  |"....to...."|
|amount     |String |Yes  |"100.0"|
|_sign      |String |Yes  |"abcd1234"|

\_\_\_\_回调 Callback\_\_\_\_
====
**请求方法：**   POST  
**路径参考：**   "<WEBSIT/IP>:<PORT>/api/transfer_Out/"  
|参数名称|类型|必填|样例|描述|
|:---- |:---:|:--:| --:| --:|
|timestamp  |String |Yes  |"1234554321"|
|user_id    |String |Yes  |"2020019428"|
|block      |String |Yes  |"Bitcoin"|
|coin_id    |String |Yes  |"BTC"|
|order_id   |String |Yes  |"abcd1234"|
|type       |String |Yes  |"full"|
|from       |String |Yes  |"....from...."|
|to         |String |Yes  |"....to...."|
|amount     |String |Yes  |"100.0"|
|_sign      |String |Yes  |"abcd1234"|
|||
|||
|||



