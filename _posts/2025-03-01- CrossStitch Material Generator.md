---
title: 十字绣程序化材质
description: 此程序化材质的目标效果为基于输入的纹理素材一键式生成布面十字绣，并暴露部分参数让美术有一定的调整自由度。
author: liangxi
date: 2025-03-01 18:30:00 +0800
categories: [SubstanceDesigner]
tags: [SubstanceDesigner, Materials]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/card_bg/2025-0301.png
  alt: Cross-stitch Material Generator created in SD.
---

<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20250301/Cross-stitch Material Vedio.mp4" type="video/mp4">

</video>

## 功能与制作思路

此程序化材质的目标效果为基于输入的纹理素材一键式生成布面十字绣，并暴露部分参数让美术有一定的调整自由度。制作思路大致拆解为以下三个部分：①背景布面纹理；②程序化生成十字绣；③十字绣图案外轮廓的单针描边。


## 背景布面纹理的制作

共制作了亚麻布面与牛仔布面两种背景布面纹理，在Pixel Processer节点内部用函数控制布面纹理tilling值，并联动暴露的background_type参数控制输出的纹理类型。

![Desktop View](/assets/img/20250301/背景布料部分.png){: width="972" height="589" }
_Background Materials Nodes_

两种布面纹理：
![Desktop View](/assets/img/20230301/T2.png){: width="972" height="589" }
_Linen_
![Desktop View](/assets/img/20230301/T3.png){: width="972" height="589" }
_Jean_

## 程序化生成十字绣

分别制作双针及三针的十字绣针脚，双针整体效果看起来更松散，三针更紧密。同样用Pixel Processer节点控制输出的针脚类型，与所暴露的boolean参数2/3Stitches联动。将输入的纹理素材转为灰度图后调整对比度，作为mask控制十字绣生成范围。在Tile Sampler节点中暴露Amount参数以调整十字绣针脚密度。将十字绣针脚部分单独输出为mask，Blend一张灰度图以调整十字绣部分的金属度、粗糙度。

### 双针与三针十字绣

![Desktop View](/assets/img/20250301/01.png){: width="972" height="589" }
_2 Types of Cross-stitch_

制作流程：
![Desktop View](/assets/img/20250301/十字绣生成部分.png){: width="972" height="589" }
_Generate Cross-stitch_

### 十字绣图案外轮廓的单针描边

制作描边部分针脚。将十字绣部分mask经过Blur后相减，得到外描边部分的mask。将Blur值暴露为描边范围的调整参数。在Pixel Processer节点内部用函数控制输出结果为一张纯黑灰度图或是外描边部分的mask，以此决定外描边的生成与否。外描边部分的mask经过Distance和Normal节点，可得到控制针脚方向的Vector Map。
同上，单针描边的颜色、金属度以及粗糙度都以Blend一张纯色图的方法控制。

![Desktop View](/assets/img/20250301/02.jpg){: width="972" height="589" }
_Outline Patches_

制作流程：
![Desktop View](/assets/img/20250301/outline_mask.png){: width="972" height="589" }
_Generate Outline Patches_

## 混合与输出

最后，将三个部分的灰度图用Max mode依次Blend，注意灰度落差，①②③部分应该由深到浅，最后得到正确的Normal map。

![Desktop View](/assets/img/20250301/Workflow.png){: width="972" height="589" }
_Blend and Finaloutput_

材质使用演示： 

{% include embed/bilibili.html id='BV17pgiz6Eyc' %}

## 效果展示

![Desktop View](/assets/img/20250301/02_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20250301/03_2K.png){: width="972" height="589" }

更完整的作品展示：[Artwork in Artstation](https://www.artstation.com/artwork/6LgwRx)




