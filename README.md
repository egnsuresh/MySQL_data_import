# MySQL_data_import
all about MySQL data import using workbench
## Overview
if you get timeout error / memory limit or similar problems, we should try following solutions for successful data import
### Temporary Fix
* while connecting workbech click on advanced tab and enter the large number for timeout
* To check allowed limit:
  * in bytes```SELECT @@max_allowed_packet;```
  * in kb ```SELECT @@max_allowed_packet / 1024;```
* to set buffer size and packet size as 200MB
  *```SET GLOBAL net_buffer_length=2000000;```
  *```SET GLOBAL max_allowed_packet=2000000000```
### Permanent Fix
* open my.cnf file (it should available in installtion folder
* find the section with following name ```[mysqld]```
* add following line in that section ```max_allowed_packet      = 200M```
