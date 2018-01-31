---
title: "Remote Linux Command"
date: 2018-01-30T19:21:45-05:00
draft: false
tags: ["Linux"]
---

I have to work on Linux Server remotely these days. So I would like to take this as a note of commands on manipulating remote files.

## `ssh` command
#### shell to login remote machine without entering password
```
set user abc123
set host 192.168.0.2
set password [your password]
set timeout -1

spawn ssh $user@$host
expect "*assword:*"
send "$password\r"
interact
expect eof
```
## `scp` command

your user name is `abc123` and you want to copy file `this.md` from your desktop to your remote machine `192.168.0.2`.
#### upload files:
`scp ~/Desktop/this.md abc123@192.168.0.2:/assignment1`
this command will copy your file `this.md` to the direction `/assignment1`.
#### download files:
`scp -r root@192.168.0.2：~/Desktop/files` this command will copy all files from your remote machine to your `/files` direction on your desktop.

## `ftp` command
to be continue...