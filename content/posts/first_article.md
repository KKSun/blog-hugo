---
title: "Hugo + Github Pages"
date: 2017-12-11T20:08:16-05:00
draft: false
tags: ["Hugo"]
catagories: ["blog & tools"]
---
## [Install Hugo](https://gohugo.io/getting-started/quick-start/)
install hugo following the instruction of the linked document is a piece of cake. [`Homebrew`](https://brew.sh/) is a fantastic tool. After installation, `Hugo new site myblog` will generate a project called `myblog` for you. `/myblog` is the source code of your blog.

## [Choose a Theme](https://themes.gohugo.io/)
actually, I don't feel those themes on Hugo official website are of good look, and some of them are not really easy to use because of their poor ducumentation. 

## [Host on Github](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
- this step is not hard but might drive you crazy when you __first__ do this following the instruction on `Github` .
- For this step, we need two repos.
- one is to hold our source code of [blog](https://github.com/KKSun/blog-hugo)
	- create an empty repo called 'myblog-hugo' on your github
	- `git clone //myblog-hugo-url//`
	- move all files your generate in myblog into this direction
	- `rm -rf public`
	- `git push`
	
- the other is used to hold the `/public` which can be generated every time you run `Hugo server` on your own computer.
 	- create a new empty repo called 'your-name.github.io'. 
 	- __NOTICE__: __'your-name' should be your github account__. 
	- `git submodule add git@github.com:your-name/your-name.github.io.git public` in your `/myblog-hugo` direction.
	- copy this file [deploy.sh](https://github.com/KKSun/blog-hugo/blob/master/deploy.sh) into `/myblog-hugo` too.
	- `chmod +x deploy.sh` to give permission to run this deploy script.
	- use `./deploy.sh` to publish any change you make about your blog with one click.


### references: 
- <http://nanshu.wang/post/2015-01-31/> 
- <http://lucumt.info/posts/create-website-with-hugo/>
