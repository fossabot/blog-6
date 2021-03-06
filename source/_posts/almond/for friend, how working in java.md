---
title: 写给我的朋友，Java学习之路
date: 2017-8-10
categories: [杂文]
tags: [杂文,学习]
---

### 最重要的

选择程序猿，便意味着你始终要学习。如果说想着看完这里的全部，就能靠这混吃一辈子，那还是放弃把。  
这里是我的曾今学习的方式，但我的学习方法可能不是很适合你。所以我只当只领路羊，接下来的学习，都得靠你自己。  
加油！

<!-- more -->

### 思维脑图

> [点这里查看图片](http://naotu.baidu.com/file/1b2db44c2a2805df3364bb7c49b9e198?token=13ccc33fc9a41655)  

这是大概的学习树，但并不全。比如maven，学java必须知道的项目构建工具，但只要了解并会简单的使用可以了，maven会随着你java的水平的提高而提高。有比如Javascript、html等前端知识，学java必须了解一些。当然学习前端，后端知识也需要懂一些。  
先看图，了解个大概，接下来我按后端学习的内容，一步一步的讲述我的经历。

### First：基础

我是科班出生的，第一次接触java是java基础课。那时候都是用java命令行操作，对java文件编译及运行。这时学习的是java的概念和基本的操作。练手的话可以写个小例子。  

> 任务1：建两个类，为苹果和香蕉，它们有编号和数量（有初始值）属性，要求分别对其实例化，控制台分别输入编号和消耗数量之后，打印剩余数量，再次要求输入编号和数量（循环）。  

第二次接触java便是web课，也是java最擅长的领域。学了java web基础servlet（等你学过去估计就忘了，当熟练主流框架后，回过来看这是满重要的），还有个已经被淘汰的框架struts2。老师也教了一个企业级的框架ssh（现在也快淘汰了），但是没听懂。这里也布置个任务  

> 任务2：用最基础的方式（jsp + servlet）实现个java web服务。  

接下来还有没有java课，没印象了，毕竟就算有，技术也熟练了应付过去没问题。  
基础部分就这样，我花了4年(其实也没那么多，印象里好像就两节android和三节java课吧)，但你肯定没那么多时间，多看看基础书把，弄清概念。任务1与2解决，基本基础过关了。  

> java基础书很多，百度以后一大把，挑新的看  

### Second：框架

框架很重要，甚至可以说你用这框架，感觉不是在写java。java里spring框架是‘轻量级’的最流行的框架。也是必学的。  
从这里开始，就需要接触maven了。java的构建方式有多种，最主要是maven（web）和gradle（android），这两个工具作用差不多，现在越来越多的人选择用gradle构建web应用。但maven仍是主流，教程多，学习的话推荐。  

> 从本质上来说：构建工具做的事是，将你现在的项目中，按照一定的规范，将文件编译后放到指定目录下，将依赖中的jar包下载下来放到指定目录下，并打包。  

它是用来替换原本的打包方式的，主要是解决各种jar包的问题，原本的打包需要自己找jar包下载，并放入指定目录。  
就框架而言，ssm现在的主流，下面的教程讲解的很明白。若是遇到不懂，解决不懂的地方，再向下看。这个视频中的js写的贼溜，这块实在看不懂可以先跳过。

#### 教程

- [慕课网：Java高并发秒杀API之业务分析与DAO层](http://www.imooc.com/learn/587)
- [慕课网：Java高并发秒杀API之业务分析与SERVICE层](http://www.imooc.com/learn/631)
- [慕课网：Java高并发秒杀API之业务分析与WEB层](http://www.imooc.com/learn/630)
- 提高：[慕课网：Java高并发秒杀API之高并发优化](http://www.imooc.com/learn/632)

> 任务3：实践很重要，跟着这个视频打一遍，并自己搭建框架实现简单的用户管理系统，要求用最新的稳定依赖。下面是maven仓库搜索地址。

- [国内maven仓库搜索](http://mvnrepository.com/)
- [官方maven仓库搜索](http://search.maven.org/)
- 还有视频中提到的[Mybatis官方文档](http://www.mybatis.org/mybatis-3/zh/index.html)
- 作为提高，再推荐一份博客，他里面对java8 Lambda讲述的很到位[lucida的博客](http://zh.lucida.me/)

### Third：Spring Boot

先来一段百科
> Spring Boot是由Pivotal团队提供的全新框架，其设计目的是用来简化新Spring应用的初始搭建以及开发过程。该框架使用了特定的方式来进行配置，从而使开发人员不再需要定义样板化的配置。通过这种方式，Spring Boot致力于在蓬勃发展的快速应用开发领域(rapid application development)成为领导者。

所以，它不是新东西，只是简化配置用的，本质上仍是spring那套。给你两份教程，学去吧。
> 任务4：学的过程中将之前的工程改成spring boot，记住之前的是ssm框架有Mybatis。

#### 资料

- 一份讲的很全的博客<http://blog.didispace.com/categories/Spring-Boot/page/4/>
- 一个慕客网上的视频：[2小时学会Spring Boot](http://www.imooc.com/learn/767) 
- 这个人的另一份视频：[Spring Boot进阶之Web进阶](http://www.imooc.com/learn/810)

到这里，回忆一下之前的最基础的servlet和jsp写的web服务，是不是有很大的不同，那么问题就来了，spring是怎么实现的
> 额外任务：参照spring mvc，写一个简单的Web应用框架，实现web请求到Controller的过程，简单点，假设参数都是string类型的。当然这个过程很困难，需要学习很多东西，如java的注解、spring mvc的原理（aop）或者说动态代理、java的反射等等。但这对于理解spring非常的有用。

### Fourth：数据库

之前的学习，已经接触数据库，写过sql了把，没什么好讲的，看书。不过作为开发增删改查会就行，查稍微麻烦点。

### Fifth：思想

呃。。先来段重构这书中的一句把
> 软件工程领域的超级经典巨著，与另壹巨著《设计模式》并称"软工双雄"，全美销量超过100000册，亚马逊书店伍星书。

这就是经典，还有代码大全，据说也是可以不断来回看

### Sixth：架构

其实到了这里，你不一定要学架构，可以继续学习java，java很难，尤其是底层，里面大量的涉及编译原理，jvm最好的虚拟机，没有之一。  

也可以走产品，你已经有代码基础了，在看些产品书，我觉得会比直接往产品方向发展更好。因为你更懂你的战友，你在设计时，也会考虑他们的情况。  

还可以dba，这玩意就要求对数据库操作很精通了。

我未来可能往架构方向发展也可能产品，目前就想多学点技术  

这里推荐个博客学习spring cloud
> 其实就是之前那个spring boot的博主<http://blog.didispace.com/categories/Spring-Cloud/>  

> 额外任务：按着教程写个一整套spring cloud玩玩，好像是这个博主出过一本书《spring cloud微服务实战》，挺不错的

### 总结

越往后，学习的路就越宽阔，学无止境。引用一句名言**吾生也有涯，而知也无涯 。以有涯随无涯，殆已！**。所以，当你完成所有任务，我便领完了路，然后各奔东西把。

### 备注

经常有人问培训怎么样，我想说有人教，比你自学肯定要快，补基础不错的，但是也很贵。但学程序后面都是靠自学，没有人教你，养成好习惯更重要，只靠培训是没用的。所以培训可去可不去。  
> 在学习java过程中，其他工具也要学学，比如git，无论你是从事什么开发，都是必备的。
