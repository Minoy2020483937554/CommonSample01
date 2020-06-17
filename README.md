服务
====

1.获取地址
----
**请求方法：**   POST  
**参考路径：**   "<WEBSIT/IP>:<PORT>/api/transfer_Out/"  
**参数列表**  
|名称|样例|
| :---: | :--: |
|timestamp|"1234554321"|
|user_id|"2020019428"|
|block|"Bitcoin"|
|_sign|"abcd1234"|
|||
|||
|||
|||
|||
|||

2.转账
----
**请求方法：**   POST  
**参考路径：**   "<WEBSIT/IP>:<PORT>/api/transfer_Out/"  
**参数列表**  
|名称|样例|
| :---: | :--: |
|timestamp|1234554321|
|user_id|2020019428|
|block|Bitcoin|
|coin_id|'BTC'|
|order_id|'abcd1234'|
|type|'full'|
|from|'....from....'|
|to|'....to....'|
|amount|'100.0'|
|_sign|'abcd1234'|

回调
====
**请求方法：**   POST  
**参考路径：**   "<WEBSIT/IP>:<PORT>/api/notification/"  
**参数列表**  
|名称|样例|
| :---: | :--: |
|timestamp|1234554321|
|user_id|2020019428|
|block|Bitcoin|
|||
|||
|||
|||
|||
|||
