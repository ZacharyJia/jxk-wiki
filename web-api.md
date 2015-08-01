# 计小科-服务器API

本页面介绍web服务器为手机API提供的各项API。web服务器为手机APP提供了文章、活动、用户信息管理等相关服务。


##1. 服务器API地址
http://bjtucit.sinaapp.com/api/服务名称.php
使用post方法请求该地址，并上传正确的参数，即可得到正确的返回值。

##2. 服务器API综述
服务器API使用PHP作为开发语言，提供了手机APP与软件交互的中间层。

##3. 身份验证
服务器API使用用户名和密码进行有效性验证，所有API共有两个参数：email和password。其中email为明文传输，password为明文密码的MD5值，确认该部分有效后，

##4. 文章部分
###1. getColumn
####名称：getColumn
#####功能：获取栏目列表。使用该API可以获取所有栏目列表及其相关的信息，包括栏目名称、栏目id、栏目简介、栏目图片。
####参数：无
####返回格式：
```
{"columns":["column1", "column2"],
 "ids":["id1", "id2"], 
 "introductions":["introduction1", "introduction2"],
 "images":["imageUrl1", "imageUrl2"]}
```

###2. login
####名称：login
####功能：用户登录。返回登录状态，用户昵称，用户学号，用户头像url，用户所在群组tag。
####参数：无
####返回格式：
```
{"status":"sucess",
 "nickname":"Zachary",
 "studentID":"13281110",
 "image":"imageUrl", 
 "tag":"bk13"}
```



