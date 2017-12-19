---
title: "Hugo + Github Pages"
date: 2017-12-11T20:08:16-05:00
draft: false
tags: ["Hugo"]
catagories: ["blog & tools"]
---
## [Install Hugo](https://gohugo.io/getting-started/quick-start/)
Install hugo following the instruction of the linked document is a piece of cake. [`Homebrew`](https://brew.sh/) is a fantastic tool for mac users. After installation,  `Hugo new site myblog`  will generate a project called  `myblog`  for you. Things in `/myblog`  is the source code of your blog.

## [Choose a Theme](https://themes.gohugo.io/)
Actually, I don't feel those themes on Hugo official website are of good look. Some of them are not really easy to use because of their poor ducumentation. Hope you can find what you want, or maybe customize a theme for yourself. 

## [Host on Github](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
- This step is not hard but might drive you crazy when you __first__ do this following the instruction on  `Github` .
- For this step, two repos are needed (This seemes a little bit strange, but trust me, this is the easiest way to handle and the simplest method to understand.)

- one is to hold our source code of [blog](https://github.com/KKSun/blog-hugo)
	- create an empty repo called 'myblog-hugo' on your github
	- `git clone //myblog-hugo-url//`
	- move all files your generate in  `/myblog`  into this cloned direction
	- `rm -rf public`
		- we will add public as a [submodule](https://git-scm.com/docs/git-submodule) of this repo, so that we can handle these two repos seperately.

	
- the other is used to hold the  `/public`  which can be generated every time you run  `Hugo server`  on your own computer.
 	- create a new empty repo called 'your-name.github.io'
 	- __NOTICE__: __'your-name' should be your github account__
 	- just like [kksun.github.io](https://github.com/KKSun/kksun.github.io)
	- in  `/myblog-hugo`  direction
		- `git submodule add git@github.com:your-name/your-name.github.io.git public`	
		- copy this file [deploy.sh](https://github.com/KKSun/blog-hugo/blob/master/deploy.sh) into  `/myblog-hugo`  as well.
	- `chmod +x deploy.sh`
		- to give permission to run this deploy script.
	- `./deploy.sh`  
		- to publish any change you make about your blog with one click.


### references: 
- <http://nanshu.wang/post/2015-01-31/> 
- <http://lucumt.info/posts/create-website-with-hugo/>
