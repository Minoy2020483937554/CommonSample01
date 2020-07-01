_0基础一二三步接入区\_块\_链主网_
***
\_\_\_\_服务 Server\_\_\_\_
====

1. **获取地址**  
    + 请求方法：   **POST**  
    + 路径参考：   "\<WEBSITE/IP\>:\<PORT\>/api/get_NewAddress/"  
    + 参数列表：  
      |名称       |描述     |类型     |必填 |样例         |取值范围|
      |:----      |:--:     |:---:   |:--: |:--         |:-- |
      |timestamp  |时间戳   |String  |Yes  |"1234554321" |---|
      |user_id    |用户名   |String  |Yes  |"2020019428" |---|
      |block      |主链名   |String  |Yes  |"Bitcoin"    |"Bitcoin"<br>"Ethereum"  |
      |type       |类型     |String  |Yes  |"full"       |"full"|
      |\_sign     |签名     |String  |Yes  |"mySign"     |---|

    + 请求返回：  
        ```javascript
        {
          "code" : 200, #int
          "msg"  : "successed", #string
          ”err"  : "null", #string
          "data" :
            {
              "address":"...ADDRESS...", #string
            },
        }
        ```

2. **转账**  
    + 请求方法：   **POST**  
    + 路径参考：   "\<WEBSITE/IP\>:\<PORT\>/api/transfer_Out/"  
    + 参数列表：  
      |名称       |描述    |类型    |必填 |样例           |取值范围|
      |:----      |:--:   |:---:   |:--: |:--           |:-- |
      |timestamp  |时间戳  |String |Yes  |"1234554321"   |---|
      |user_id    |用户名  |String |Yes  |"2020019428"   |---|
      |block      |主链名  |String |Yes  |"Bitcoin"      |"Bitcoin"<br>"Ethereum"|
      |coin_id    |货币名  |String |Yes  |"BTC"          |"BTC"<br>"ETHER"<br>"USDT"|
      |order_id   |订单号  |String |Yes  |"..orderid.."  |---|
      |type       |类型    |String |Yes  |"full"         |"full"|
      |from       |发送者  |String |Yes  |"...from..."   |---|
      |to         |接收者  |String |Yes  |"...to..."     |---|
      |amount     |数额    |String |Yes  |"100.0"        |---|
      |\_sign     |签名    |String |Yes  |"mySign"       |---|

    + 请求返回：  
        ```javascript
        {
          "code" : 200, #int
          "msg"  : "successed", #string
          ”err"  : "null", #string
          "data" : "null", #string
        }
        ```

\_\_\_\_回调 Callback\_\_\_\_
====

3. 通知  
    + 请求方法：   **POST**  
    + 路径参考：   "\<WEBSITE/IP\>:\<PORT\>/api/notification/"  
    + 参数列表：  
      |名称       |描述   |类型   |必填  |样例         |取值范围|
      |:----      |:--:  |:---:  |:--:  |:--         |:-- |
      |timestamp  |时间戳 |String |Yes  |"1234554321" |---|
      |status     |状态   |String |Yes  |"pending"    |"pending"<br>"confirmed"<br>"secured"<br>"cancelled"|
      |block      |主链名 |String |Yes  |"Bitcoin"    |"Bitcoin"<br>"Ethereum"|
      |coin_id    |货币名 |String |Yes  |"BTC"        |"BTC"<br>"ETHER"<br>"USDT"|
      |app_id     |应用名 |String |Yes  |"Test_APP"   |---自定义---|
      |order_id   |订单号 |String |Yes  |"..orderid.."|---|
      |hash       |哈希值 |String |Yes  |"...hash..." |---|
      |type       |类型   |String |Yes  |"Tx_In"      |"Tx_In"<br>"Tx_Out"|
      |from       |发送者 |String |No   |"...from..." |---|
      |to         |接收者 |String |Yes  |"...to..."   |---|
      |amount     |数额   |String |Yes  |"100.0"      |---|
      |\_sign     |签名   |String |Yes  |"mySign"     |---|

    + 请求返回：  
        ```javascript
        {
          "code" : 200, #int
          "msg"  : "successed", #string
          ”err"  : "null", #string
          "data" : "null", #string
        }
        ```
