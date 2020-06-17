服务 Server
====

1.获取地址
----
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

2.转账
----
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

\_回调 Callback
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
