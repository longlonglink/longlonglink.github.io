---
layout: post
title: "image-to-latex教程"
date: 2023-04-18
description: ''
tags:
- 工具
categories:
- docker
---
* ##动机
最近在复习教材知识点，要写数学公式，但是写latex实在是太复杂了，

于是去找能不能直接生成latex
代码的工具，于是就找到了GitHub上的这个开源项目。

 [image-to-latex](https://github.com/kingyiusuen/image-to-latex)

********
* ##docker安装
  普通安装方法仓库的readme写的很清楚了，我是用docker装的，就帮大家先把坑踩了。
1. 先拉取并运行镜像
 ````
          docker pull dhusr/image-to-latex:latest
          
          docker run -d -p 8000:8000 -p 8501:8501 dhusr/image-to-latex
  ````        
2. 使用potainer网页exec进入容器，安装必要的文件
![](/assets/img/sharding-gerenciamento-usuarios/image-latex.png)
````
        apt install -y make wget 
 
        mkdir streamlit

        cd streamlit 
 
        wget https://raw.githubusercontent.com/kingyiusuen/image-to-latex/main/streamlit/app.py
````
3. 启动网页服务
````
        cd ..

        make streamlit
````
![](/assets/img/sharding-gerenciamento-usuarios/image-latex-2.png)
4. 用浏览器访问docker主机ip地址，端口号8501
![](assets/img/sharding-gerenciamento-usuarios/image-latex-1.png)
******
* ## 测试
  试了几张图片，识别单个公式比较有效，多个公式就容易出错。不过毕竟是开源项目，能做到这样也不错了。