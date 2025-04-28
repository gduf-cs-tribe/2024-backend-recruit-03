# 2024-backend-recruit-03
# 24届爪哇部落后端第三轮考核

- [方向介绍](#方向介绍)
- [考核说明](#考核说明)
- [注意事项](#注意事项)
- [项目要求](#项目要求⭐⭐)
- [提交方式](#提交方式)
- [写在最后](#写在最后)

## 方向介绍

文档中包含 Java，C/C++，go三个方向的推荐网课，学习资料，发展路径等相关内容

- [direction-introduction](direction-introduction)

## 考核说明

- 本次考核根据上一轮的情况，我们这次会把考核分为三个**Level**：

  - [24级爪哇后端第三轮考核Level1](2024-backend-recruit-03-Level1.md)
  - [24级爪哇后端第三轮考核Level2](2024-backend-recruit-03-Level2.md)
  - [24级爪哇后端第三轮考核Level3](2024-backend-recruit-03-Level3.md)

- **Level1**的内容与**第一轮考核**相同：
  - Level1涉及的内容是**基础知识**，熟悉语言基础是学习一门语言中极为重要的，level1的内容可以协助你很快的上手一门语言语法，并且找到自己感兴趣的方向。
  - Level1**并非强制**要求完成，如果你已经掌握了Level1的内容且愿意尝试Level2的内容，我们允许不提交Level1。
  
- **Level2**的内容与**第二轮考核**相同：

  - Level2的完成需要确定好语言的选择，并且熟悉一些数据结构和对api的使用，有能力的同学可以尝试提交Level2。
  - Level2也是**并非强制**要求完成，但是需要熟悉好语言语法，并且能了解后端大致学习内容

- **Level3是本次的**主要考核内容：

  - 根据不同的语言方向规划出不同的考核，详细查看具体的考核文档


## **注意事项**

1. 已经提交考核需要选择至少**选择下一Level的内容**进行考核，**不允许进行两次提交都是一个Level**的。
2. 无论完成哪个考核任务，请先完整阅读完**所有编码要求**之后再开始！
3. 至少需要完成**Level2级别以上且代码质量足够高**才有可能获得面试机会。
4. 本次考核由于时间比较紧张且**Level3**难度较大，可能无法完成全部内容，此时需要及时将**阶段性产物**提交上来。

## 项目要求⭐⭐

标准的仓库应该是什么样子：

- https://github.com/denoland/deno
- https://github.com/vuejs/vue
- https://gitee.com/dromara/sa-token

上诉项目，能够将每次的阶段性产物提交仓库，同时每次commit都能清晰的说明这次提交做了什么，并且项目的**`README`**等文档写的非常详细，能够指引阅读者怎么使用你的项目，这是很重要的一点。

我们在阅读上一次的考核时，当我们克隆仓库后，出现了大量的**文件缺失、环境缺失、缺少依赖、项目结构混乱、单文件庞大、无法运行等**情况，导致难以阅读。

因此我们要求提交上来的仓库能够有完整且详细的**`README`**等文档，以及尽可能做到每次完成部分功能就将代码提交到git仓库，避免只在最后将整个项目一次性的上传。

1. 使用 git 作为本次项目的版本控制工具，并将**源代码**放到 github/gitee 上面托管，请不要将IDE交上来，并且对于每次的commit要做好解释。
   - 什么是 git ? 请参考下列相关资料，加上自行谷歌。
      - [Git的介绍以及基本使用 - 掘金](https://juejin.cn/post/7246313318544834615?searchId=2023102323355872C532323C258A9E0350)
      - [Git到底是什么?](https://www.bilibili.com/read/cv15412717/)
   - 什么是 github ？
      - [Github 是什么，有什么用？](https://github-zh.com/post/what-is-github)
   - 其他资料
      - 官方文档 ： [Git - Book](https://git-scm.com/book/zh/v2/)
      - 使用心得：[git使用心得](https://wumingsheng.gitbooks.io/-git/content/)
2. 使用 **MarkDown** **语法** 书写考核所需要的所有文档。并提交 .md 格式的文档
   - 什么是 MarkDown ? [什么是 MarkDown](https://www.zhihu.com/question/19963642)
   - 推荐的 MarkDown 语法编辑器：Typora，Obsidian
3. 代码规范参考
   - Java：[《阿里巴巴 Java 开发手册》](https://kangroo.oschina.io/ajcg)
   - C: [《OpenHarmony C语言编程规范》](https://gitee.com/openharmony/docs/blob/master/zh-cn/contribute/OpenHarmony-c-coding-style-guide.md)
   - C++: [《Google C++ 风格指南》](https://zh-google-styleguide.readthedocs.io/en/latest/google-cpp-styleguide/contents/)
   - Golang: [《Go 语言编码规范》](https://learnku.com/go/wikis/38426)

## 提交方式

1. github/gitee 仓库地址，仓库内容包括：
   1. **源代码** （Talk is cheap, show me the code）
   2. README.md 文件：使用 **MarkDown** 语法书写的项目介绍文档，内容包括:
      1. 项目介绍
      2. 项目使用的语言，用到了该语言的什么语法、特性等
      3. 完成的功能
   3. 注意：
      1. README.md 中的图片一定要确保可以被访问到，不要出现图片路径是本地路径这种低级错误。建议在仓库中开一个`image`文件夹来放置所有图片。
      2. 请确保你的仓库被设置为 **public**, 以便我们访问你的仓库。（gitee 的仓库默认为 private，记得修改）
   
2. 请在第三轮考核截止日期之前，将仓库地址通过问卷的方式提交给我们。
   1. 提交地址：https://fcnkfgz1xonr.feishu.cn/share/base/form/shrcnUPGVY1U4OTcgcuy7XyNUVe
   
   2. 邮箱内容
      1. 你的仓库地址，例如：
         https://github.com/username/yourRepositorieName
         https://gitee.com/username/yourRepositorieName
         注意将仓库权限设置为public，将提交的代码放在main/master分支
   
      2. 另外有一个想对我们说的话部分：你可以谈谈，项目的设计思路、过程中遇到的问题、一些心得体会、对爪哇部落的印象等，都可以写到这部分。
   
   3. 问卷中将收集你的联系方式，请一定要认真填写，确保我们可以联系到你，以进行接下来的面试。
   
   4. 截止时间：**2025.6.1 18:00**

## 写在最后

​		参加考核的师弟师妹们！无论最终结果如何，你们在考核过程中付出的努力、突破的瓶颈、学到的技能，都是成长路上最珍贵的礼物。这些收获远比结果更重要，它们将成为你们未来发展的坚实基石。知识或许会更新迭代，但解决问题的能力、坚韧的品格和持续学习的习惯，才是超越考核的永恒礼物。

