---
title: "Fix_catalina"
date: 2020-04-18T22:20:57-04:00
draft: false
tags: ["Mac"]
---

## Cannot build C program after upgrade to MacOS-10.15

### Why

This is because apple change the path to the clang, those fundamental things are collected into `/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk`

### Following these steps

- open terminal and install xcode developer tools by 

`xcode-select --install`

- make link in `/usr/local/include/`

`sudo ln -s /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include/* /usr/local/include/`

- all set