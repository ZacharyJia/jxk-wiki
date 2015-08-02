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

###1. login
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
###2. getColumn
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

###3. getNewest
####名称：getNewest
####功能：获取最新文章。返回文章标题，文章id，文章图片，文章所属栏目，文章内容
####参数：
`offset`：数字类型 文章列表的偏移量，即已经获取过的文章的数量，API将从该offset开始获取之前的**10条**文章并返回。
####返回格式：
```
{“titles”:["title1", "title2",...],
 "ids":["id1", "id2", ...]
 "images":["imageUrl1", "imageUrl2", ...]
 "columns":["column1", "cokumn2", ...]
 "contents":["content1", "content2", ...]}
```

###4. getHotArticle
####名称：getHotArticle
####功能：获取最热文章列表。返回文章标题，文章id，文章图片，文章所属栏目，文章内容。
####参数：
`offset`：数字类型 文章列表的偏移量，即已经获取过的文章的数量，API将从该offset开始获取之前的**10条**文章并返回。
####返回格式：
```
{“titles”:["title1", "title2",...],
 "ids":["id1", "id2", ...]
 "images":["imageUrl1", "imageUrl2", ...]
 "columns":["column1", "cokumn2", ...]
 "contents":["content1", "content2", ...]}
```

###5. getArticle
####名称：getArticle
####功能：返回一篇文章的详细内容和评论内容的HTML内容。用于以web方式展示详细内容。
####参数：
`id`：数字类型 文章的id
####返回格式：
网页代码

###6. getEventList
####名称：getEventList
####功能：返回当前正在进行或即将开始的活动列表。包括活动名称、活动id、活动起止时间、活动举办单位、活动图片。
####参数：
`offset`：数字类型 文章列表的偏移量，即已经获取过的活动的数量，API将从该offset开始获取之前的**10个**活动并返回。
####返回格式：
```
{"ids":["id1", "id2", ...],
 "names":["name1", "name2", ...],
 "start_times":["start_time1", "start_time2", ...],
 "end_times":["end_time1", "end_time2", ...],
 "sponsors":["sponsor1", "sponsor2", ...],
 "images":["imageUrl1", "imageUrl2", ...]
}
```

###7. getEventDetail
####名称：getEventDetail
####功能：返回活动详情信息的网页格式。
####参数：
`id`：数字类型 活动的id
####返回格式：
网页代码

###8. getHistoryEvent
####名称：getEventList
####功能：返回当前已经结束的活动列表。包括活动名称、活动id、活动起止时间、活动举办单位、活动图片。
####参数：
`offset`：数字类型 文章列表的偏移量，即已经获取过的活动的数量，API将从该offset开始获取之前的**10个**活动并返回。
####返回格式：
```
{"ids":["id1", "id2", ...],
 "names":["name1", "name2", ...],
 "start_times":["start_time1", "start_time2", ...],
 "end_times":["end_time1", "end_time2", ...],
 "sponsors":["sponsor1", "sponsor2", ...],
 "images":["imageUrl1", "imageUrl2", ...]
}
```

###9. joinEvent
####名称：joinEvent
####功能：用户参加此活动
####参数：
`eventID` 数字类型 要参与的活动的ID
####返回格式：
成功
```
{"status":"success"}
```

错误
```
{"status":"error"}
```

###10. unjoinEvent
####名称：unjoinEvent
####功能：用户取消参与活动
####参数：
`eventID` 数字类型 要参与的活动的ID
####返回格式：
成功
```
{"status":"success"}
```

错误
```
{"status":"error"}
```

