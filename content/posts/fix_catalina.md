---
title: "Fix MacOS 10.15 Clang Link"
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

### （Update） Install Ruby with `rbenv`

`rbenv` directly compile Ruby from source code. Therefore, we can still see some core files are missing in `/usr`. To install ruby, `$(xcrun --show-sdk-path)/usr/include/` should be linked as `/usr/include` with `csrutil` disabled. [about csrutil](https://ss64.com/osx/csrutil.html) 

The scripts below should be put into `~/.zshrc`. Comment these lines out after ruby is installed or it might influnce original C/C++ environment.

```
# Setup Compiler paths for readline and openssl 
local READLINE_PATH=$(brew --prefix readline)
local OPENSSL_PATH=$(brew --prefix openssl)
export LDFLAGS="-L$READLINE_PATH/lib -L$OPENSSL_PATH/lib"
export CPPFLAGS="-I$READLINE_PATH/include -I$OPENSSL_PATH/include"
export PKG_CONFIG_PATH="$READLINE_PATH/lib/pkgconfig:$OPENSSL_PATH/lib/pkgconfig"

# Use the OpenSSL from Homebrew instead of ruby-build
# Note: the Homebrew version gets updated, the ruby-build version doesn't
export RUBY_CONFIGURE_OPTS="--with-openssl-dir=$OPENSSL_PATH"

# Place openssl@1.1 at the beginning of your PATH (preempt system libs)
export PATH=$OPENSSL_PATH/bin:$PATH

# Set SDKROOT
export SDKROOT="$(xcrun --show-sdk-path)"
```

