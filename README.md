# NodeLearning

![](https://img2023.cnblogs.com/blog/2332774/202211/2332774-20221129194058382-1820521834.png)

**说明：本仓库是Node.js相关知识的学习总结**

## 简介

`Node.js`发布于2009年5月，由`Ryan Dahl`开发，是一个基于`Chrome V8`引擎的`JavaScript运行环境`，使用了一个`事件驱动`、`非阻塞式I/O模型`，让JavaScript 运行在服务端的开发平台，它让JavaScript成为与PHP、Python、Perl、Ruby等服务端语言平起平坐的脚本语言。
`Node.js`对一些特殊用例进行优化，提供替代的API，使得V8在非浏览器环境下运行得更好，V8引擎执行Javascript的速度非常快，性能非常好，基于Chrome JavaScript运行时建立的平台， 用于方便地搭建响应速度快、易于扩展的`网络应用`。

## 发展历程

- 2009年2月，Ryan Dahl在博客上宣布准备基于V8创建一个轻量级的Web服务器并提供一套库。
- 2009年5月，Ryan Dahl在GitHub上发布了最初版本的部分Node包，随后几个月里，有人开始使用Node开发应用。
- 2009年11月和2010年4月，两届JSConf大会都安排了Node.js的讲座。
- 2010年年底，Node获得云计算服务商Joyent资助，创始人Ryan Dahl加入Joyent全职负责Node的发展。
- 2011年7月，Node在微软的支持下发布Windows版本。
- 2016年，leftpad事件，Yarn诞生
- 2021年，发布最新版本Node.js 17。

## 主要功能

V8引擎本身使用了一些最新的编译技术。这使得用Javascript这类脚本语言编写出来的代码运行速度获得了极大提升，又节省了开发成本。对性能的苛求是`Node`的一个关键因素。 Javascript是一个事件驱动语言，`Node`利用了这个优点，编写出可扩展性高的服务器。`Node`采用了一个称为“事件循环(event loop）”的架构，使得编写可扩展性高的服务器变得既容易又安全。提高服务器性能的技巧有多种多样。`Node`选择了一种既能提高性能，又能减低开发复杂度的架构。这是一个非常重要的特性。并发编程通常很复杂且布满地雷。`Node`绕过了这些，但仍提供很好的性能。

`Node`采用一系列“非阻塞”库来支持事件循环的方式。本质上就是为文件系统、数据库之类的资源提供接口。向文件系统发送一个请求时，无需等待硬盘（寻址并检索文件），硬盘准备好的时候非阻塞接口会通知`Node`。该模型以可扩展的方式简化了对慢资源的访问， 直观，易懂。尤其是对于熟悉onmouseover、onclick等DOM事件的用户，更有一种似曾相识的感觉。

虽然让Javascript运行于服务器端不是`Node`的独特之处，但却是其一强大功能。不得不承认，浏览器环境限制了我们选择编程语言的自由。任何服务器与日益复杂的浏览器客户端应用程序间共享代码的愿望只能通过Javascript来实现。虽然还存在其他一些支持Javascript在服务器端 运行的平台，但因为上述特性，`Node`发展迅猛，成为事实上的平台。

在`Node`启动的很短时间内，社区就已经贡献了大量的扩展库（模块）。其中很多是连接数据库或是其他软件的驱动，但还有很多是凭他们的实力制作出来的非常有用的软件。

最后，不得不提到的是`Node`社区。虽然`Node`项目还非常年轻，但很少看到对一个项目如此狂热的社区。不管是新手，还是专家，大家都围绕着项目，使用并贡献自己的能力，致力于打造一个探索、支持、分享、听取建议的乐土。

## 运行环境

`Node`作为一个新兴的前端框架，后台语言，有很多吸引人的地方：RESTful API，单线程。

`Node`可以在不新增额外线程的情况下，依然可以对任务进行并发处理 —— `Node.js`是`单线程的`。它通过事件循环（event loop）来实现并发操作，对此，我们应该要充分利用这一点 —— 尽可能的避免阻塞操作，取而代之，多使用非阻塞操作。

## 功能模块

`Node`使用Module模块去划分不同的功能，以简化应用的开发。Modules模块有点像C++语言中的类库。每一个`Node`的类库都包含了十分丰富的各类函数，比如http模块就包含了和http功能相关的很多函数，可以帮助开发者很容易地对比如http,tcp/udp等进行操作，还可以很容易的创建http和tcp/udp的服务器。

要在程序中使用模块是十分方便的，只需要如下：

在这里，引入了http类库，并且对http类库的引用存放在http变量中了。这个时候，`Node`会在我们应用中搜索是否存在`Node`_modules的目录，并且搜索这个目录中是否存在http的模块。如果`Node`.js找不到这个目录，则会到全局模块缓存中去寻找，用户可以通过相对或者绝对路径，指定模块的位置，比如：
var myModule = require('./myModule.js');
模块中包含了很多功能代码片断，在模块中的代码大部分都是私有的，意思是在模块中定义的函数方法和变量，都只能在同一个模块中被调用。当然，可以将某些方法和变量暴露到模块外，这个时候可以使用exports对象去实现。

## 应用方向

具备书写JavaScript的IDE，普通的记事本也可以进行开发。在几年的时间里，`Node.JS`逐渐发展成一个成熟的开发平台，吸引了许多开发者。有许多大型高流量网站都采用Node.JS进行开发，此外，开发人员还可以使用它来开发一些快速移动Web框架。

除了Web应用外，NodeJS也被应用在许多方面，`NodeJS`也可以在在其它方面所开发的神奇的项目，这些项目涉及到应用程序监控、媒体流、远程控制、桌面和移动应用等等。

### AcquaintanceNode

**初识Node.js相关内容学习笔记**

**学习目标**

- 能够知道什么是Node.js
- 能够知道Node.js可以做什么
- 能够说出Node.js 中的JavaScript的组成部分
- 能够使用fs模块读写操作文件
- 能够使用path模块处理路径
- 能够使用http模块写一个基本的web 服务器

**学习目录**

- 初识Node.js
- fs文件系统模块
- path路径模块
- http模块