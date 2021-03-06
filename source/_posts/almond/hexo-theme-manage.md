---
title: 简单、高效的管理hexo站点主题
date: 2018-10-15
categories: [Web]
tags: [Hexo,CI]
---
如果您和我一样，喜欢更新至最新的主题，那么您也应该遇到和我一样的烦恼。每次更新新的主题时，总是要重新配置，而且随着自定义的内容增多，更新就成了负担。   
因此，引入了Fork与Submodules来实现以下目标
1. 自动合并自定义内容与配置
2. 校验更新操作是否正常工作

> 如果您不了解如何使用hexo搭建博客，您可以参考这篇博客：<https://jiangtj.gitlab.io/articles/almond/gitlab-pages-for-hexo/>

<!-- more -->

# GitHub Fork
Fork，一般用在贡献开源项目时（这里由于需要对主题配置做修改）。  
1. 找到您喜欢的主题的开源项目，并点击fork，派生该项目至您自己的远程仓库
![GitHub Fork](https://upload-images.jianshu.io/upload_images/2360355-f174e793318476af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2. 创建新的分支例如custom，并在新分支上调整您的配置

完成上述步骤后，以后每次合并新的功能仅仅是将主题的改动合并到自己的远程仓库，然后合并到分支上即可。避免了每次做同样的修改操作

# Git Submodules
通过fork，我们得到了想要的主题，但如何使用呢？通常的做法是下载主题到hexo博客项目中，测试并部署。然后，Git合并并不能保证永远完美的工作，如果出现问题，就需要修改主题项目，重新下载放入hexo工程，在运行测试。这过程是复杂的    
事实上，Git已经针对这种依赖另一个独立的Git仓库情况作了调整，来解决复杂项目管理问题，而这种方式是Submodules子模块    
> Git 通过子模块来解决这个问题。 子模块允许你将一个 Git 仓库作为另一个 Git 仓库的子目录。 它能让你将另一个仓库克隆到自己的项目中，同时还保持提交的独立。  ---ProGit(中文版)    


1. 添加您的子模块
```bash
git submodule add <remote-url> <local-path>
```
2. 进去您的字模块，切换到自定义分支，其他操作，就像普通的Git项目一样  


如果您使用vs code，那么在侧边栏Git里，可以很方便的可视化管理子模块
![vs code](https://upload-images.jianshu.io/upload_images/2360355-c30f56ee049cbddc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这样之后，您的更新操作，也变得足够简单，基本自定义的配置错了，也可以直接对子模块做修改并提交

# GitLab CI
在gitlab ci中需要针对子模块做额外的配置，将`GIT_SUBMODULE_STRATEGY`变量改为`normal`或者`recursive`
```yml
variables:
  GIT_SUBMODULE_STRATEGY: recursive
```
# 参考
1. [GitHub - 对项目做出贡献](https://git-scm.com/book/zh/v2/GitHub-%E5%AF%B9%E9%A1%B9%E7%9B%AE%E5%81%9A%E5%87%BA%E8%B4%A1%E7%8C%AE)
2. [Git 工具 - 子模块](https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E5%AD%90%E6%A8%A1%E5%9D%97)
3. [Using Git submodules with GitLab CI](https://docs.gitlab.com/ee/ci/git_submodules.html#using-git-submodules-in-your-ci-jobs)

