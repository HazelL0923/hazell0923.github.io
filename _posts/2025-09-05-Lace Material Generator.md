---
title: 蕾丝布料程序化材质
description: >-
  此程序化材质的目标效果为基于输入的纹理素材一键式生成蕾丝布料，并暴露部分参数让美术有一定的调整自由度。

author: cotes
date: 2025-09-05 21:30:00 +0800
categories: [SubstanceDesigner]
tags: [SubstanceDesigner, Materials]
pin: true
post_card_image: /assets/img/card_bg/2025-0905.png
---



<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20250905/Lace_Artstation.mp4" type="video/mp4">

</video>


制作思路大致拆解为以下三个部分：①对输入纹理进行基于灰度的分层处理，输出为独立的mask；②制作图案的外描边刺绣；③程序化生成五种蕾丝纹理并添加每一个灰度层的独立控制，可以自定义每一层的蕾丝图案类型和Tiling值。
*本文所展示的最终渲染效果基于网络上下载的图案，灰度是使用floodfill进行填充的随机值，在项目中使用可以在绘制图案时按照设计自行填充好灰度后再输入。

### 对输入纹理进行分层处理

基于灰度值进行分层（灰度值每增加0.2为一层，当然可以更多）。

![layer separate](/assets/img/20250905/LayerSeparate.jpg)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; _Layer Separate nodes_


### 五种蕾丝纹理
![Patterns](/assets/img/20250905/BasePattern.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_5 BasePatterns_


### 混合与输出
![Blend and Output](/assets/img/20250905/Workflow.jpg)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_All workflow nodes_
材质使用演示： [Material Preview in BiliBili](https://www.bilibili.com/video/BV18a42zwEJn/?spm_id_from=333.1387.upload.video_card.click&vd_source=4172e98a5ea7a742809137ec6ad74e83)

### 效果展示
![FinalOutput](/assets/img/20250905/01_2K.png)
![FinalOutput](/assets/img/20250905/02_2K.png)
![FinalOutput](/assets/img/20250905/03_2K.png)
![FinalOutput](/assets/img/20250905/04_2K.png)
![FinalOutput](/assets/img/20250905/05_2K.png)
![FinalOutput](/assets/img/20250905/06_2K.png)
更完整的作品展示：[Artwork in Artstation](https://www.artstation.com/artwork/rlNgAe)


[nodejs]: https://nodejs.org/
[starter]: https://github.com/cotes2020/chirpy-starter
[pages-workflow-src]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow
[docker-desktop]: https://www.docker.com/products/docker-desktop/
[docker-engine]: https://docs.docker.com/engine/install/
[vscode]: https://code.visualstudio.com/
[dev-containers]: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
[dc-clone-in-vol]: https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-a-git-repository-or-github-pr-in-an-isolated-container-volume
[dc-open-in-container]: https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-an-existing-folder-in-a-container
