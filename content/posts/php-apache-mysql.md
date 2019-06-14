---
title: "Php & Apache & Mysql"
date: 2019-06-13T20:33:07-04:00
draft: false
---

## Environment for DiscuzX3.0 on Ubuntu

### Install php5.6

#### Add source first

`sudo add-apt-repository ppa:ondrej/php`

#### Install 
```
sudo apt-get update
sudo apt-get install -y php5.6
```

### Mysql5.7 install
```
sudo apt-get install mysql
sudo mysql -u root
```
in mysql use this line to set password for `root`
```
UPDATE mysql.user SET plugin="mysql_native_password",   
authentication_string=PASSWORD("password") WHERE user="root";   
SET GLOBAL validate_password_policy=0;   
```
restart, then you can login as root with password

```
sudo service mysql restart
```

### Apache is easy

```
sudo apt-get install apache2
```


### DiscuzX3.0

Download from `http://download.comsenz.com/DiscuzX/3.0/Discuz_X3.0_SC_UTF8.zip`

unzip first, put all the files and directories in `/var/www/html/bbs`

```
sudo chown -R jason:jason /var/www/html/
chmod -R 755 /var/www/html
chmod -R 777 /var/www/html/bbs # for the installation on website
```

#### fix `mysql_connect()`

`sudo apt-get install php5.6-mysql`

#### fix `xml_parser_create()`

`sudo apt-get install php5.6-xml`

### Finally

Go to `your_domain/bbs` to initiate your website!