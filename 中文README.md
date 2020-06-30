_0基础一二三步接入区\_块\_链主网_
***
\_\_\_\_服务 Server\_\_\_\_
====

1. **获取地址**  
    + 请求方法：   **POST**  
    + 路径参考：   "\<WEBSIT/IP\>:\<PORT\>/api/get_NewAddress/"  
    + 参数列表：  
      |名称       |描述     |类型     |必填 |样例         |取值范围                  |
      |:----      | --     |:---:    |:--: |:--         |:--                       |
      |timestamp  |时间戳   |String  |Yes  |"1234554321" |---                      |
      |user_id    |用户名   |String  |Yes  |"2020019428" |---                      |
      |block      |主链名   |String  |Yes  |"Bitcoin"    |"Bitcoin"<br>"Ethereum"  |
      |type       |类型     |String  |Yes  |"full"       |"full"                   |
      |\_sign     |签名     |String  |Yes  |"mySign"     |---                      |

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
    + 路径参考：   "\<WEBSIT/IP\>:\<PORT\>/api/transfer_Out/"  
    + 参数列表：  
      |名称  |类型  |必填| 样例|描述|
      |:---- |:---:|:--:| --:| --:|
      |timestamp  |String |Yes  |"1234554321" |时间戳  |
      |user_id    |String |Yes  |"2020019428" |用户名  |
      |block      |String |Yes  |"Bitcoin"    |主链名  |
      |coin_id    |String |Yes  |"BTC"        |货币名  |
      |order_id   |String |Yes  |"..orderid.."|订单号  |
      |type       |String |Yes  |"full"       |类型    |
      |from       |String |Yes  |"...from..." |发送者  |
      |to         |String |Yes  |"...to..."   |接收者  |
      |amount     |String |Yes  |"100.0"      |数额    |
      |\_sign     |String |Yes  |"mySign"     |签名    |

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
    + 路径参考：   "\<WEBSIT/IP\>:\<PORT\>/api/notification/"  
    + 参数列表：  
      |名称  |类型  |必填| 样例|描述|
      |:---- |:---:|:--:| --:| --:|
      |timestamp  |String |Yes  |"1234554321" |时间戳 |
      |status     |String |Yes  |"pending"    |状态   |
      |block      |String |Yes  |"Bitcoin"    |主链名 |
      |coin_id    |String |Yes  |"BTC"        |货币名 |
      |app_id     |String |Yes  |"Test_APP"   |应用名 |
      |order_id   |String |Yes  |"..orderid.."|订单号 |
      |type       |String |Yes  |"full"       |类型   |
      |from       |String |No   |"...from..." |发送者 |
      |to         |String |Yes  |"...to..."   |接收者 |
      |amount     |String |Yes  |"100.0"      |数额   |
      |\_sign     |String |Yes  |"mySign"     |签名   |

    + 请求返回：  
        ```javascript
        {
          "code" : 200, #int
          "msg"  : "successed", #string
          ”err"  : "null", #string
          "data" : "null", #string
        }
        ```
