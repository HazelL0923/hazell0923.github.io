---
title: 蕾丝布料程序化材质
description: 此程序化材质的目标效果为基于输入的纹理素材一键式生成蕾丝布料，并暴露部分参数让美术有一定的调整自由度。
author: liangxi
date: 2025-09-05 20:30:00 +0800
categories: [SubstanceDesigner]
tags: [SubstanceDesigner, Materials]
pin: false
math: true
mermaid: true
image:
  path: /assets/img/card_bg/2025-0905.png
  alt: Lace Material Generator created in SD.
---

<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20250905/Lace_Artstation.mp4" type="video/mp4">

</video>

## 功能与制作思路

此程序化材质的目标效果为基于输入的纹理素材一键式生成蕾丝布料，并暴露部分参数让美术有一定的调整自由度。制作思路大致拆解为以下三个部分：①对输入纹理进行基于灰度的分层处理，输出为独立的mask；②制作图案的外描边刺绣；③程序化生成五种蕾丝纹理并添加每一个灰度层的独立控制，可以自定义每一层的蕾丝图案类型和Tiling值。
*本文所展示的最终渲染效果基于网络上下载的图案，其灰度是使用floodfill进行填充的随机值，在项目中使用时可以自行填充好灰度后再输入，以得到更准确的效果。


## 对输入纹理进行分层处理

基于灰度值进行分层（灰度值每增加0.2为一层，当然可以更多）。

![Desktop View](/assets/img/20250905/LayerSeparate.jpg){: width="972" height="589" }
_Layer Separating_

## 五种蕾丝纹理
![Desktop View](/assets/img/20250905/BasePattern.png){: width="972" height="589" }
_5 BasePatterns_

## 制作全流程

![Desktop View](/assets/img/20250905/Workflow.jpg){: width="972" height="589" }
_The Entire Workflow_

材质使用演示： 

{% include embed/bilibili.html id='BV18a42zwEJn' %}

## 效果展示

![Desktop View](/assets/img/20250905/01_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20250905/02_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20250905/03_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20250905/04_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20250905/05_2K.png){: width="972" height="589" }

![Desktop View](/assets/img/20250905/06_2K.png){: width="972" height="589" }

更完整的作品展示：[Artwork in Artstation](https://www.artstation.com/artwork/rlNgAe)




