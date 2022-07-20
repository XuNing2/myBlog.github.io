---
title: fastgithub 的使用
date: 2022-04-06 12：00：00
tags: hexo
description: 在hexo 中插入图片的尝试
---
## 原因

在用到实验室服务器的时候，不可避免地需要github的服务，例如上传代码啥的，经常会碰到上传不了的问题。

[]截图

## fastgithub 使用方法

[FastGithub 地址](https://github.com/dotnetcore/FastGithub)

~~~bash
wget https://github.com/dotnetcore/FastGithub/releases/download/2.1.4/fastgithub_linux-x64.zip
unzip fastgithub_linux-x64.zip
rm fastgithub_linux-x64.zip
cd fastgithub_linux-x64
sudo ./fastgithub
或者 sudo ./fastgithub start

~~~

可能因为服务器是docker 容器，服务器运行 sudo ./fastgithub start 其实没有这个服务，实测也用不了代理，所以我使用了命令

~~~bash
sudo ./fastgithub # 先写入证书
ctrl+c 中断
nohup ./fastgithub &
~~~

写入 服务器代理

~~~bash
export all_proxy="http://127.0.0.1:38457"

#或者全局生效

svim /etc/profile    #编辑全局配置文件
#在末尾添加 export all_proxy="http://127.0.0.1:38457"
source /etc/profile    #试配置文件生效
# https://www.cnblogs.com/sinicheveen/p/13641007.html
~~~