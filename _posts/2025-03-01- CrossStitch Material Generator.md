---
title: 十字绣程序化材质
description: >-
  此材质的目标效果为基于输入的纹理素材一键式生成布面十字绣。&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;

author: cotes
date: 2025-03-01 15:00:00 +0800
categories: [SubstanceDesigner]
tags: [SubstanceDesigner, Materials]
pin: true
post_card_image: /assets/img/card_bg/2025-0301.png
---



<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20250301/Cross-stitch Material Vedio.mp4" type="video/mp4">

</video>


制作思路大致拆解为以下三个部分：①背景布面纹理；②程序化生成十字绣；③十字绣图案外轮廓的单针描边。

### 背景布面纹理的制作

制作了亚麻布面与牛仔布面两种背景布面纹理，在Pixel Processer节点内部用函数控制布面纹理tilling值，并联动暴露的background_type参数控制输出的纹理类型。

![background workflow](/assets/img/20250301/背景布料部分.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; _background nodes_


两种布面纹理：
![background Type2](/assets/img/20230301/T2.png)
![background Type3](/assets/img/20230301/T3.png)


### 程序化生成十字绣
分别制作双针及三针的十字绣针脚，双针整体效果看起来更松散，三针更紧密。同样用Pixel Processer节点控制输出的针脚类型，与所暴露的boolean参数2/3Stitches联动。将输入的纹理素材转为灰度图后调整对比度，作为mask控制十字绣生成范围。在Tile Sampler节点中暴露Amount参数以调整十字绣针脚密度。将十字绣针脚部分单独输出为mask，Blend一张灰度图以调整十字绣部分的金属度、粗糙度。

双针与三针的十字绣：
![2or3 Stitches](/assets/img/20250301/01.png)
![2or3 Stitches nodes](/assets/img/20250301/十字绣生成部分.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_Stitches nodes_

### 十字绣图案外轮廓的单针描边
制作描边部分针脚。将十字绣部分mask经过Blur后相减，得到外描边部分的mask。将Blur值暴露为描边范围的调整参数。在Pixel Processer节点内部用函数控制输出结果为一张纯黑灰度图或是外描边部分的mask，以此决定外描边的生成与否。外描边部分的mask经过Distance和Normal节点，可得到控制针脚方向的Vector Map。
同上，单针描边的颜色、金属度以及粗糙度都以Blend一张纯色图的方法控制。

外轮廓单针描边:
![Outline](/assets/img/20250301/02.jpg)
![Outline nodes](/assets/img/20230301/Type2.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_Outline nodes_

### 混合与输出
最后，将三个部分的灰度图用Max mode依次Blend，注意灰度落差，①②③部分应该由深到浅，最后得到正确的Normal map。
![Blend](/assets/img/20250301/Workflow.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_Blend and FinalOutput_

材质使用演示： [Material Preview in BiliBili](https://www.bilibili.com/video/BV17pgiz6Eyc/?spm_id_from=333.1387.upload.video_card.click&vd_source=4172e98a5ea7a742809137ec6ad74e83)

### 效果展示
![FinalOutput](/assets/img/20250301/02_2K.png)
![FinalOutput](/assets/img/20250301/03_2K.png)

更完整的作品展示：[Artwork in Artstation](https://www.artstation.com/artwork/6LgwRx)


[nodejs]: https://nodejs.org/
[starter]: https://github.com/cotes2020/chirpy-starter
[pages-workflow-src]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow
[docker-desktop]: https://www.docker.com/products/docker-desktop/
[docker-engine]: https://docs.docker.com/engine/install/
[vscode]: https://code.visualstudio.com/
[dev-containers]: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
[dc-clone-in-vol]: https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-a-git-repository-or-github-pr-in-an-isolated-container-volume
[dc-open-in-container]: https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-an-existing-folder-in-a-container
