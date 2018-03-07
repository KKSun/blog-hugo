---
title: "Delete_mysql"
date: 2018-03-07T02:14:36-05:00
draft: false
tags: ["mac"]
---
## Delete and re-install `Mysql`

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

### Re-install `Mysql` via `brew`
```
brew install mysql
```
After the installation, we can start mysql server by running 
```
mysql.server start
```
The benefit of `brew` appears after this step, because we can directly setup the initialization of `Mysql` by running
```
mysql_secure_installation
```
Following the steps and everything will be all set.

#### Reference
[mac安装与卸载mysql方法](http://blog.csdn.net/liumaolincycle/article/details/51896592)
[mac上使用brew安装mysql的后续](https://segmentfault.com/q/1010000004078668)