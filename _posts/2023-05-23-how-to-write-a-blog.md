---
layout:     post
title:      "Python中的简单人脸检测"
subtitle:   ""
author:     "zcc"
header-img: "img/bg-1.png"
header-mask:  0.5
catalog: true
tags:
    - 笔记
---

## Python中的简单人脸检测
利用markdown教程（<[https://www.runoob.com](https://www.runoob.com/markdown/md-link.html)>）试作第一篇博客

## 正文

### 1、 代码

```javascript
import cv2,os
# path = '/tmp'
# retval = os.getcwd()
# print(f'当前工作目录为{retval}')
# Load the cascade
face_cascade = cv2.CascadeClassifier('face_detector.xml')
# img
img = cv2.imread('test.png')
# 检测人脸
face = face_cascade.detectMultiScale(img, 1.1, 4)
# Draw rectangle around the faces
for (x, y, w, h) in face:
	cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
# Exporttheresult
cv2.imwrite("face_detected.png", img)
print('Successfully saved')
```
### 2、面部检测模型
创建文本文档，复制[链接]([链接地址](https://raw.githubusercontent.com/opencv/opencv/master/data/haarcascades/haarcascade_frontalface_default.xml))中的面部检测模型代码，另存为“face_detector.xml”

