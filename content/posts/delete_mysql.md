---
title: "Delete_mysql"
date: 2018-03-07T02:14:36-05:00
draft: false
tags: ["mac"]
---

### Way to completely delete `Mysql` on Macbook
 It is hard to delete `Mysql` completely on mac, because it is not in `/Application ` folder and it has many parts deperated in different places. 
 
### Following the terminal command below
```
sudo rm /usr/local/mysql
sudo rm -rf /usr/local/mysql*
sudo rm -rf /Library/StartupItems/MySQLCOM
sudo rm -rf /Library/PreferencePanes/My*

vim /etc/hostconfig 
/*
remove the line "MYSQLCOM=-YES-" and save the file
if you do not have this file before just skip this step
*/

rm -rf ~/Library/PreferencePanes/My*
sudo rm -rf /Library/Receipts/mysql*
sudo rm -rf /Library/Receipts/MySQL*
sudo rm -rf /var/db/receipts/com.mysql.*
```
 Finally, `Mysql` will be deleted completely.

#### Reference
[mac安装与卸载mysql方法](http://blog.csdn.net/liumaolincycle/article/details/51896592)