---
title: 布面刺绣程序化材质
description: >-
  此材质的目标效果为基于输入的纹理素材一键式生成布面刺绣。&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;

author: cotes
date: 2023-03-01 18:55:00 +0800
categories: [SubstanceDesigner]
tags: [SubstanceDesigner, Materials]
pin: true
#img_path:  /_posts/20230301/
post_card_image: /assets/img/card_bg/2023-0301.png
---



<video width="100%" height="auto" controls muted autoplay loop>
  <source src="/assets/img/20230301/Select a file name for output files_001.mp4" type="video/mp4">

</video>


制作思路大致拆解为以下两个部分：①背景布面纹理；②程序化生成三种刺绣图案。

### 背景布面纹理的制作

制作了毛毡、亚麻布面、牛仔布面与丝绸四种背景布面纹理，在Pixel Processer节点内部用函数控制布面纹理tilling值，并联动暴露的background_type参数控制输出的纹理类型。

![background workflow](/assets/img/20230301/Background.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; _background nodes_


四种布面纹理：
![background Type1](/assets/img/20230301/T1.png)
![background Type2](/assets/img/20230301/T2.png)
![background Type3](/assets/img/20230301/T3.png)
![background Type4](/assets/img/20230301/T4.png)

### 程序化生成三种刺绣
Type1.短针刺绣：
![Patches Type1](/assets/img/20230301/Type1Patches.png)
![Patches Type1 nodes](/assets/img/20230301/Type1.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_Patches Type1 nodes_

Type2.描边部分刺绣:
![Patches Type2 nodes](/assets/img/20230301/Type2Patches.png)
![Patches Type2](/assets/img/20230301/Type2.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_Patches Type2 nodes_

Type3.最常见的密集针脚刺绣:
![Patches Type3 nodes](/assets/img/20230301/Type3Patches.png)
![Patches Type3](/assets/img/20230301/Type3.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_Patches Type3 nodes_

### 更多参数设置
为刺绣部分设置更多参数以生成更丰富的效果：如刺绣针脚长度、刺绣部分粗糙度和金属度、刺绣部分颜色等。
![workflow](/assets/img/20230301/SD_workflow.png)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;_All workflow nodes_
材质使用演示： [Material Preview in BiliBili](https://www.bilibili.com/video/BV1XDgvzhE2m/?spm_id_from=333.1387.upload.video_card.click&vd_source=4172e98a5ea7a742809137ec6ad74e83)

### 效果展示
![FinalOutput](/assets/img/20230301/01_2K.png)
![FinalOutput](/assets/img/20230301/03_2K.png)
![FinalOutput](/assets/img/20230301/04_2K.png)
![FinalOutput](/assets/img/20230301/05_2K.png)
![FinalOutput](/assets/img/20230301/06_2K.png)
更完整的作品展示：[Artwork in Artstation](https://www.artstation.com/artwork/qJXRby)


[nodejs]: https://nodejs.org/
[starter]: https://github.com/cotes2020/chirpy-starter
[pages-workflow-src]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow
[docker-desktop]: https://www.docker.com/products/docker-desktop/
[docker-engine]: https://docs.docker.com/engine/install/
[vscode]: https://code.visualstudio.com/
[dev-containers]: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
[dc-clone-in-vol]: https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-a-git-repository-or-github-pr-in-an-isolated-container-volume
[dc-open-in-container]: https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-an-existing-folder-in-a-container
