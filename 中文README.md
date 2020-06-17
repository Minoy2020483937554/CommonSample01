_0基础一二三步接入区\_块\_链主网_
***
\_\_\_\_服务 Server\_\_\_\_
====

1. ### 获取地址  
    + **请求方法：**   POST  
    + **路径参考：**   "<WEBSIT/IP>:<PORT>/api/get_NewAddress/"  
    + **参数列表：**  
      |名称  |类型  |必填| 样例|描述|
      |:---- |:---:|:--:| --:| --:|
      |timestamp  |String |Yes  |"1234554321" |实时时间戳  |
      |user_id    |String |Yes  |"2020019428" |用户名      |
      |block      |String |Yes  |"Bitcoin"    |区块链类型  |
      |type       |String |Yes  |"full"       |类型       |
      |\_sign     |String |Yes  |"abcd1234"   |签名       |

    + 请求返回：  
        ```javascript
        {
          "code"   : 200,#int
          "msg"    : "successed",#string
          "result" :
            {
              "address":"...ADDRESS...",#string
            },
        }
        ```

2. ### 转账  
    + **请求方法：**   POST  
    + **路径参考：**   "<WEBSIT/IP>:<PORT>/api/transfer_Out/"  
    + **参数列表：**  
      |名称  |类型  |必填| 样例|描述|
      |:---- |:---:|:--:| --:| --:|
      |timestamp  |String |Yes  |"1234554321" |实时时间戳  |
      |user_id    |String |Yes  |"2020019428" |用户ID     |
      |block      |String |Yes  |"Bitcoin"    |区块链类型  |
      |coin_id    |String |Yes  |"BTC"        |货币ID     |
      |order_id   |String |Yes  |"abcd1234"   |订单号     |
      |type       |String |Yes  |"full"       |类型       |
      |from       |String |Yes  |"...from..." |发送者     |
      |to         |String |Yes  |"...to..."   |接收者     |
      |amount     |String |Yes  |"100.0"      |数额       |
      |\_sign     |String |Yes  |"abcd1234"   |签名       |

    + 请求返回：  
        ```
        {
          "code"   : 200,#int
          "msg"    : "successed",#string
          "result" :
            {
              "address":"...ADDRESS...",#string
            },
        }
        ```

\_\_\_\_回调 Callback\_\_\_\_
====

3. ### 转账  
    + **请求方法：**   POST  
    + **路径参考：**   "<WEBSIT/IP>:<PORT>/api/notification/"  
    + **参数列表：**  
      |名称  |类型  |必填| 样例|描述|
      |:---- |:---:|:--:| --:| --:|
      |timestamp  |String |Yes  |"1234554321" ||
      |user_id    |String |Yes  |"2020019428" ||
      |block      |String |Yes  |"Bitcoin"    ||
      |coin_id    |String |Yes  |"BTC"        ||
      |order_id   |String |Yes  |"abcd1234"   ||
      |type       |String |Yes  |"full"       ||
      |from       |String |Yes  |"...from..." ||
      |to         |String |Yes  |"...to..."   ||
      |amount     |String |Yes  |"100.0"      ||
      |\_sign     |String |Yes  |"abcd1234"   ||

    + 请求返回：  
        ```
        {
          "code"   : 200,#int
          "msg"    : "successed",#string
          "result" :
            {
              "address":"...ADDRESS...",#string
            },
        }
        ```
