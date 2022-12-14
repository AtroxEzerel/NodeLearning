# 初识Node

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

## 一. 初识Node.js

### 1. 回顾与思考

1. 已经掌握的技术
- HTML
- CSS
- JavaScript

2. 浏览器中的JavaScript的组成部分

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221028002717029-838952518.png)

3. 为什么JavaScript可以在浏览器中执行

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221028002813229-2108827400.png)

不同的浏览器使用不同的JAcaScripr解析引擎

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221028002926301-339774684.png)

4. 为什么JavaScript可以操作DOM和BOM

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221028003228980-304067726.png)

每个浏览器都`内置`了DOM、BOM这样的API函数，因此，浏览器中的JavaScript才可以调用它们。

5. 浏览器中的JavaScript运行环境

`运行环境`是指****代码正常运行所需的必要环境。**

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221028003604467-8109644.png)

- v8引擎负责解析和执行JavaScript 代码。
- 内置API是由`运行环境`提供的特殊接口，`只能在所属的运行环境中被调用`。

6. 思考:JavaScript能否做后端开发

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221028003919537-2038072318.png)

JavaScript也可以做后端开发但需要借助Node.js的开发环境。

### 2. Node.js 简介

1. 什么是Node.js

Node.js is a `JavaScript runtime` built on Chrome's V8 JavaScript engine.

`Node.js`是一个基于Chrome V8引擎的`JavaScript运行环境`。

Node.js 的官网地址: https://nodejs.org/zh-cn/

2.Node.js 中的JavaScript运行环境

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221030225855786-1687655964.png)

注意:
- `浏览器`是JavaScript 的`前端运行环境`。
- `Node.js`是JavaScript的`后端运行环境`。

Node.js 中`无法调用`DOM和BOM等`浏览器内置API`。

3. Node.js 可以做什么

Node,js作为一个JavaScript的运行环境，仅仅提供了基础的功能和API。然而，基于Nodejs 提供的这些基础能，很多强大的工具和框架如雨后春笋，层出不穷，所以学会了Node.js，可以让前端程序员胜任更多的工作和岗位:

- 基于Express框架(http://www.expressjs.com.cn/)，可以快速构建Web应用
- 基于Electron框架(https://electronjs.org/)，可以构建跨平台的桌面应用
- 基于restify框架(http://restify.com/)，可以快速构建API接口项目
- 读写和操作数据库、创建实用的命令行工具辅助前端开发、etc...

总之: Nodejs 是大前端时代的“大宝剑”，有了Nodejs这个超级buff的加持，前端程序员的行业竞争力会越来越强!

4. Node.js好学吗

好学!
JavaScript，就能学会Node.js! !!

5. Node.js怎么学

浏览器中的JavaScript学习路径:JavaScript 基础语法＋浏览器内置API(DOM + BOM)+第三方库 (jQuery、art-template等)

Node.js 的学习路径:`JavaScript 基础语法`＋`Node.js 内置API模块`（fs、path、http等)＋`第三方API模块`(express、mysql等)

### 3. Node.js环境的安装

安装包可以从Node.js 的官网首页直接下载，进入到Node.,js 的官网首页(https://nodejs.org/en/)，点击绿色的按钮，下载所需的版本后，双击直接安装即可。

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221030230944258-1739670214.png)

1. 区分LTS版本和 Current版本的不同
- LTS为长期稳定版，对于追求稳定性的企业级项目来说，推荐安装LTS版本的Node.js。
- Current为新特性尝鲜版，对热衷于尝试新特性的用户来说，推荐安装Current版本的Node,js。但是，Current 版本中可能存在隐藏的Bug 或安全性漏洞，因此不推荐在企业级项目中使用Current版本的Node.js.


2. 查看已安装的Node.js的版本号

打开终端，在终端输入命令node -v后，按下回车键，即可查看已安装的Node.js的版本号。

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221030231911410-41900046.png)

Windows系统快速打开终端的方式:
使用快捷键(Windows徽标键＋R)打开运行面板，输入cmd后直接回车，即可打开终端。

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221030231953323-723232027.png)

3. 什么是终端

![](https://img2022.cnblogs.com/blog/2332774/202210/2332774-20221030231953323-723232027.png)

终端(英文: Terminal)是专门为开发人员设计的，`用于实现人机交互`的一种方式。

作为一名合格的程序员，我们有必要识记一些`常用的终端命令`，来辅助我们更好的操作与使用计算机。

### 4. 在Node.js环境中执行JavaScript代码
- 打开终端win+cmd(选中文件shift+鼠标右键 点击进入 Powershell 窗口)
- 输入node要执行的js文件的路径
-  node NodejsRunJavaScript.js

1. 终端中的`快捷键`

在Windows的powershell或cmd终端中，我们可以通过如下快捷键，来提高终端的操作效率:

- 使用`↑键`，可以快速定位到上一次执行的命令。
- 使用`tab键`，能够快速补全路径。
- 使用`esc键`，能够快速清空当前已输入的命令。
- 输入`cls命令`，可以清空终端。

## 二. fs文件系统模块

### 1. 什么是fs文件模块
`fs 模块`是Node,js 官方提供的、用来操作文件的模块。它提供了一系列的方法和属性，用来满足用户对文件的操作需求。
- fs.readFile0方法，用来读取指定文件中的内容
- fs.writeFile(方法，用来向指定的文件中写入内容

如果要在JavaScript 代码中，使用fs模块来操作文件，则需要使用如下的方式先导入它:

```js
const fs = require('fs')
```

### 2.读取指定文件中的内容

1. fs.readFile()的语法格式

使用fs.readFile(方法，可以读取指定文件中的内容，语法格式如下:

```js
fs.readFile(path[, options], callback)
```

参数解读
- 参数1:`必选`参数，字符串，表示文件的路径。
- 参数2:可选参数，表示以什么`编码格式来`读取文件。
- 参数3:`必选`参数，文件读取完成后，通过回调函数拿到读取的结果。

2. fs.readFile()的示例代码

以utf8 的编码格式，读取指定文件的内容，并打印err 和dataStr的值:

```js
//2.调用fs.readFile()方法读取文件
/* 
参数1：读取文件的存放路径
参数2：读取文件的编码格式，一般指定 utf8
参数3：回调函数，拿到读取失败和成功的结果 err dataStr
 */

fs.readFile('./files/11.txt', 'utf-8', function (err, dataStr) {
    //打印失败的结果
    console.log(err);//如果读取成功则err的值为null 如果读取失败则打印错误信息
    console.log('------');
    //打印成功的结果
    console.log(dataStr);//如果读取失败则dataStr为undefined
})
/* 
null
------
2022年11月13日 
*/  
```

3. 判断文件是否读取成功

可以判断err 对象是否为null，从而知晓文件读取的结果:

```js
const fs = require('fs')

fs.readFile('./files/11.txt', 'utf-8', function (err, dataStr) {
    if (err) {
        return console.log('读取文件失败！' + err.message);
    }

    console.log('读取文件成功！', dataStr);
})
//读取文件失败！ENOENT: no such file or directory, open 'e:\web-study\NodeLearning\AcquaintanceNode\files\11.txt'

fs.readFile('./files/1.txt', 'utf-8', function (err, dataStr) {
    if (err) {
        return console.log('读取文件失败！' + err.message);
    }

    console.log('读取文件成功！', dataStr);
})
//读取文件成功！ 2022年11月13日
```
### 3.向指定的文件中写入内容

1. fs.writeFile()的语法格式

使用fs.writeFile(方法，可以向指定的文件中写入内容，语法格式如下:

```js
fs.writeFile(file,data[,options],callback)
```
参数解读
- 参数1:`必选`参数，需要指定一个`文件路径的字符串`，表示文件的存放路径。
- 参数2:`必选`参数，表示要写入的内容。
- 参数3:`可选`参数，表示以什么格式写入文件内容，默认值是utf8。

2. fs.writeFile()的示例代码

```js
fs.writeFile('./files/2.txt', '2022/11/29', function (err) {
    /* 
    2.1如果文件写入成功，则err返回null
    2.2如果文件写入失败，则err的值等于一个错误对象
     */
    console.log(err);
})
```

3. 判断文件是否写入成功

可以判断err对象是否为null，从而知晓文件写入的结果:

```js
if (err) {
    return console.log('文件写入失败：' + err.message);
}
console.log('文件写入成功');
```

### 4. fs文件系统模块使用

使用fs文件系统模块，将素材目录下3.txt文件中的考试数据，整理到4.txt文件中。

`整理前`
```json
小红=99 小白=100 小黄=70 小黑=66 小绿=88
```
`整理后`
```js
[ '小红:99', '小白:100', '小黄:70', '小黑:66', '小绿:88' ]
```
**核心实现步骤**
- 导入需要的fs文件系统模块
- 使用fs.readFile(方法，读取素材目录下的3.txt文件
- 判断文件是否读取失败
- 文件读取成功后，处理成绩数据
- 将处理完成的成绩数据，调用fs.writeFile)方法，写入到新文件4.txt中

### 5. fs模块-路径动态拼接问题

在使用fs模块操作文件时，如果提供的操作路径是以`./`或`../`开头的`相对路径`时，很容易出现路径动态拼接错误的问题。

原因:代码在运行的时候，`会以执行node命令时所处的目录`，动态拼接出被操作文件的完整路径。

解决方案:在使用fs模块操作文件时，`直接提供完整的路径`，不要提供.』或../开头的相对路径，从而防止路径动态拼接的问题,

```js
/* 
__dirname 表示当前文件所处的目录
 */
console.log({ __dirname });//{ __dirname: 'e:\\web-study\\NodeLearning\\AcquaintanceNode' } 
fs.readFile(__dirname + '/files/2.txt', 'utf-8', function (err, dataStr) {
    if (err) {
        return console.log('读取文件失败！' + err.message);
    }

    console.log('读取文件成功！', dataStr);
})
```
