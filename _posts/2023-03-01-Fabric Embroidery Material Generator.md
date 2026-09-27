---
title: 布面刺绣程序化材质
description: 此程序化材质的目标效果为基于输入的纹理素材一键式生成布面刺绣，并暴露部分参数让美术有一定的调整自由度。
author: liangxi
date: 2023-03-01 18:30:00 +0800
categories: [SubstanceDesigner]
tags: [SubstanceDesigner, Materials]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/card_bg/2023-0301.png
  alt: Fabric Embroidery Material Generator created in SD.
---

<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20230301/Select a file name for output files_001.mp4" type="video/mp4">

</video>

## 功能与制作思路

此程序化材质的目标效果为基于输入的纹理素材一键式生成布面刺绣，并暴露部分参数让美术有一定的调整自由度。制作思路大致拆解为以下两个部分：①背景布面纹理；②程序化生成三种刺绣图案。


## 背景布面纹理的制作

共制作了毛毡、亚麻布面、牛仔布面与丝绸四种背景布面纹理，在Pixel Processer节点内部用函数控制布面纹理tilling值，并联动暴露的background_type参数控制输出的纹理类型。

![Desktop View](/assets/img/20230301/Background.png){: width="972" height="589" }
_Background Materials Nodes_

四种布面纹理：
![Desktop View](/assets/img/20230301/T1.png){: width="972" height="589" }
_Felt_
![Desktop View](/assets/img/20230301/T2.png){: width="972" height="589" }
_Linen_
![Desktop View](/assets/img/20230301/T3.png){: width="972" height="589" }
_Jean_
![Desktop View](/assets/img/20230301/T4.png){: width="972" height="589" }
_Silk_

## 程序化生成三种刺绣

### Type1.短针刺绣
![Desktop View](/assets/img/20230301/Type1Patches.png){: width="972" height="589" }
_Type1 Patches_

制作流程：
![Desktop View](/assets/img/20230301/Type1.png){: width="972" height="589" }
_Type1 Patches workflow_

### Type2.描边刺绣
![Desktop View](/assets/img/20230301/Type2Patches.png){: width="972" height="589" }
_Type2 Patches_

制作流程：
![Desktop View](/assets/img/20230301/Type2.png){: width="972" height="589" }
_Type2 Patches workflow_

### Type3.密集针脚刺绣
![Desktop View](/assets/img/20230301/Type3Patches.png){: width="972" height="589" }
_Type3 Patches_

制作流程：
![Desktop View](/assets/img/20230301/Type3.png){: width="972" height="589" }
_Type3 Patches workflow_

## 更多参数设置

为刺绣部分设置更多参数以生成更丰富的效果：如刺绣针脚长度、刺绣部分粗糙度和金属度、刺绣部分颜色等。
![Desktop View](/assets/img/20230301/SD_workflow.png){: width="972" height="589" }
_Parameters setting_

材质使用演示： 

{% include embed/bilibili.html id='BV1XDgvzhE2m' %}

## 效果展示

![Desktop View](/assets/img/20230301/01_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20230301/03_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20230301/04_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20230301/05_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20230301/06_2K.png){: width="972" height="589" }

更完整的作品展示：[Artwork in Artstation](https://www.artstation.com/artwork/qJXRby)




