---
title: 照片素材转风格化贴图工具
description: 此程序化工具用于将项目组外出采风拍摄的照片素材作为输入、以项目风格为参考生成风格化贴图。
author: liangxi
date: 2022-07-01 21:00:00 +0800
categories: [SubstanceDesigner]
tags: [SubstanceDesigner, Materials, SubstancePainter]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/card_bg/2022-0701.png
  alt: Photo material to Stylized texture tool created in SD.
---

## 使用演示

### 用于扫描模型资产

<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20220701/RealistictoStylistic2.mp4" type="video/mp4">

</video>

<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20220701/RealistictoStylistic3.mp4" type="video/mp4">

</video>

<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20220701/RealistictoStylistic1.mp4" type="video/mp4">

</video>

### 用于照片资产

<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20220701/RealistictoStylistic4.mp4" type="video/mp4">

</video>

## 目标功能

项目组想要尝试将外出采风时拍摄的大量照片素材通过程序化工具一键式生成风格化贴图，要尽量贴合项目的手绘质感风格，能够在去除照片中大部分写实细节的同时，保留体积感与颜色变化的丰富度。

## 制作思路

为了达到项目要求的简洁的风格化效果，我对照片先进行了多次去噪，尽量只保留大色块，并加入了笔刷效果打造手绘质感；由于所有的input只是一张照片素材，无法获得准确的法线信息来生成用于塑造体积感的AOmap，我的解决策略是生成一个深色的选区，再对这个选区进行更细腻的风格化处理（可以调整该选区的去噪程度、明度、色相等），从而与底色的大色块产生对比，增加体积感。


## 底色生成

照片素材进行处理前后对比：

![Desktop View](/assets/img/20220701/BaseColor处理前后对比.jpg){: width="972" height="589" }
_Base Color_

可通过以下参数调整底色的色块大小、笔刷纹理强度、色块模糊度等。

![Desktop View](/assets/img/20220701/Basecolor_parameters.jpg){: width="972" height="589" }
_Basecolor parameters_


## 深色选区

深色选区的处理：

![Desktop View](/assets/img/20220701/Shadow使用步骤.jpg){: width="972" height="589" }
_Dark area process_

可通过以下参数调整深色选区的范围、去噪程度、笔刷强度、明度等。

![Desktop View](/assets/img/20220701/Shadow_parameters.jpg){: width="972" height="589" }
_Shadow parameters_


## 效果展示

### 照片素材

![Desktop View](/assets/img/20220701/02.png){: width="972" height="589" }

![Desktop View](/assets/img/20220701/03.png){: width="972" height="589" }

![Desktop View](/assets/img/20220701/01.png){: width="972" height="589" }

![Desktop View](/assets/img/20220701/04.jpg){: width="972" height="589" }

### 扫描模型资产

![Desktop View](/assets/img/20220701/模型效果对比01.jpg){: width="972" height="589" }

![Desktop View](/assets/img/20220701/模型效果对比02.jpg){: width="972" height="589" }

![Desktop View](/assets/img/20220701/模型效果对比03.jpg){: width="972" height="589" }

![Desktop View](/assets/img/20220701/模型效果对比04.jpg){: width="972" height="589" }




