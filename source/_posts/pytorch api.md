~~~
title: 服务器杂记
date: 2022-06-06 16:40:39
tags: ubuntu
description: 接触到的一些问题
~~~

## kaggle api 在 colab上

~~~python
!mkdir ~/.kaggle
!touch ~/.kaggle/kaggle.json

api_token = {"username":"livelove","key":"179d8a4f8b02cb9a917b2d5c9b4c01b0"}

import json

with open('/root/.kaggle/kaggle.json', 'w') as file:
    json.dump(api_token, file)

!chmod 600 ~/.kaggle/kaggle.json
~~~

## 挂载谷歌云盘

~~~python
from google.colab import drive
drive.mount('/content/gdrive')
~~~

## 下载 UCF101 数据集

~~~bash
!kaggle datasets download -d pevogam/ucf101-frames
!unzip /content/ucf101-frames.zip
!rm /content/ucf101-frames.zip
!mkdir ucf101
!mv test/* ucf101
!rsync -a /content/train /content/ucf101
~~~



