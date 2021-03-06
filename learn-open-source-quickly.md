> From Docker and Kubernetes under the Hood

快速熟悉一个开源项目一般分为查阅文档、动手实践、源码阅读三个阶段

# 第一步：查阅文档

阅读文档包括查阅项目文档和博客，最好是*带着问题*去阅读。

1. 查阅文档与博客

  快速阅读介绍开源项目的架构、使用方法，大体了解该项目的意义、功能和基本使用方法。着眼于了解全貌。
  确定是自己想要的项目，便可以开始耐心的阅读项目提供的文档，学习下载、安装和使用方法。


2. 带着问题去阅读

* 这个项目解决了什么问题
* 这个项目涉及哪些成熟的技术
* 这个项目是否符合我的要求（用户规模、使用场景、性能、安全性等）
* 阅读完文档后，能否尝试画出大致的架构图


# 第二步：动手实践

阅读文档的过程中，按照文档的操作指南亲手实践，既加深实践，同时会注意到很多细节，可以更清晰感受到项目是否符合自己的需求。

1.搭建项目

  阅读README，进行部署安装和尝试。按照示例代码进行尝试，进而根据自己的理解对实例代码进行修改。出现问题通过以下渠道快速解决：

* google.com
* stackoverflow.com
* groups.google.com
* github.com issues

2.深层次改动

  很多开源项目都会提供 release 版本。如果基本的部署已经成功的话，*强烈建议*尝试从源码构建和部署改项目。这样就能够从开发、
  调试到发布整个一体化的全部过程，全方位感受项目的优缺点。

基本的尝试过后，可以开始使用一些高级功能，如一些高级配置，较为复杂的API等。


# 第三步：阅读源码

  经过上述两个步骤后，项目的大致情况已经了然于胸，更为深入的了解必然得通过阅读源码：根据命令行的代码调式过程阅读；或者根据架构分块阅读。

1.跟着运行过程阅读

  适合于刚上手，通过实践对某个命令或参数的理解。从主干开始，逐步理清命令在运行过程中代码的调用路径。通过 debug 工具观察变量和函数、
  修改源码打印日志、可以更好的帮助阅读源码。

*当理清楚这个过程后*，可以将这个过程用流程图的形式记录下来，从而加深印象，方便下次阅读的时候快速回忆和对比。

2.分模块阅读

  在理清楚程序运行的基本流程后，可以根据你架构上各个模块的作用，挑选感兴趣的部分阅读，如网络、通信、用户接口、界面等，选择一个模块，深入细节当中。
  此时也可以带着如下问题帮助自己理解：

* 调用了什么底层库
* 采用了什么设计模式
* 这么写有什么好处

如果在阅读的过程中出现了瓶颈，一时无法理解，不妨去阅读相关的单元测试。一个好的单元测试通常都描述了要测试代码的主要功能和数据便捷，
通过运行和理解单元测试，可以有效的帮助理解源码。

最后，为开源项目贡献你的力量。
