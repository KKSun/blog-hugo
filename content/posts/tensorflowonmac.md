---
title: "Try Tensorflow on mac"
date: 2018-03-30T16:33:37-04:00
draft: false
tags: ["Tensorflow"]
---

## Use `Tensorflow` on my Macbook

### two ways to install	
- docker
- virtualenv

### use virtualenv to install `Tensorflow`
- first we get python and pip with us via `brew` on mac

```
-> python3 --verion
Python 3.6.4
-> pip3 --version
pip 9.0.1 from /usr/local/lib/python3.6/site-packages (python 3.6)
```

- use pip to install `virtualenv`

```
pip3 install --upgrade virtualenv
```

- after we get `virtualenv`, use this tool to create a virtual environment of tensoflow

```
-> virtualenv --system-site-packages -p python3 ./tensorflow
```

- finally work on tensorflow virtual environment, you will get a notation ahead your terminal direction

```
-> workon tensorflow
(tensorflow) -> 
```

### Later on we will play with docker

learning docker ...

### Output sample after 400 iterations

##### style:
![style](/Users/brencharlson/Documents/Python-workspace/neural-style/examples/2-style2.jpg)
##### input:
![input](/Users/brencharlson/Documents/Python-workspace/neural-style/examples/photo.jpg)
##### output:
![input](/Users/brencharlson/Documents/Python-workspace/neural-style/examples/newpic.jpg)
