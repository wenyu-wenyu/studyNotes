# 一、初识 Node.js

# 1 、回顾与思考

## 1.1. 已经掌握了哪些技术

<img src="images\01node\2022-03-10_184937.png" style="zoom: 50%;" />

## 1.2 浏览器中的 JavaScript 的组成部分

![](images\01node\2022-03-10_185133.png)

## 1.3. 思考：为什么 JavaScript 可以在浏览器中被执行

不同的浏览器使用不同的 JavaScript 解析引擎：

-  Chrome 浏览器 => V8 

- Firefox 浏览器 => OdinMonkey（奥丁猴） 

-  Safri 浏览器 => JSCore 

-  IE 浏览器 => Chakra（查克拉） 

-  etc... 

- 其中，Chrome 浏览器的 V8 解析引擎性能最好！

  <img src="images\01node\2022-03-10_185232.png" style="zoom: 80%;" />

## 1.4思考：为什么 JavaScript 可以操作 DOM 和 BOM

​	每个浏览器都**内置了 DOM、BOM 这样的 API 函数**，因此，浏览器中的 JavaScript 才可以调 用它们。

<img src="images\01node\2022-03-10_185554.png" style="zoom:80%;" />

## 4.5浏览器中的 JavaScript 运行环境

​	**运行环境是指代码正常运行所需的必要环境。**

![](images\01node\2022-03-10_185716.png)

**总结：**

1.   V8 引擎负责解析和执行 JavaScript 代码。
2. 内置 API 是由运行环境提供的特殊接口， 只能在所属的运行环境中被调用。

## 4.6思考：JavaScript 能否做后端开发

![](images\01node\2022-03-10_185837.png)

# 2、 Node.js 简介

## 2.1什么是 Node.js Node.js

-  is a JavaScript runtime built on Chrome's V8 JavaScript engine. 

- Node.js 是一个基于 Chrome V8 引擎的 JavaScript 运行环境。

-  Node.js 的官网地址： https://nodejs.org/zh-cn/

## 2.2Node.js 中的 JavaScript 运行环境

<img src="images\01node\2022-03-10_190055.png" style="zoom:80%;" />

**注意：** 

-  浏览器是 JavaScript 的前端运行环境。 
-  Node.js 是 JavaScript 的后端运行环境。 
- Node.js 中无法调用 DOM 和 BOM 等 浏览器内置 API。

## 2.3Node.js 可以做什么 

​	Node.js 作为一个 JavaScript 的运行环境，仅仅提供了基础的功能和 API。然而，基于 Node.js 提供的这些基础能，很多强大 的工具和框架如雨后春笋，层出不穷，所以学会了 Node.js ，可以让前端程序员胜任更多的工作和岗位：

-  基于 Express 框架（http://www.expressjs.com.cn/），可以快速构建 Web 应用 

-  基于 Electron 框架（https://electronjs.org/），可以构建跨平台的桌面应用 

-  基于 restify 框架（http://restify.com/），可以快速构建 API 接口项目 

-  读写和操作数据库、创建实用的命令行工具辅助前端开发、etc… 

  总之：Node.js 是大前端时代的“大宝剑”，有了 Node.js 这个超级 buff 的加持，前端程序员的行业竞争力会越来越强！

## 2.4Node.js 怎么学

-  浏览器中的 JavaScript 学习路径： JavaScript 基础语法 + 浏览器内置 API（DOM + BOM） + 第三方库（jQuery、art-template 等） 
- Node.js 的学习路径： JavaScript 基础语法 + Node.js 内置 API 模块（fs、path、http等）+ 第三方 API 模块（express、mysql 等）

# 3、Node.js 环境的安装 

​	如果希望通过 Node.js 来运行 Javascript 代码，则必须在计算机上安装 Node.js 环境才行。 安装包可以从 Node.js 的官网首页直接下载，进入到 Node.js 的官网首页（https://nodejs.org/en/），点击 绿色的按钮，下载所需的版本后，双击直接安装即可

<img src="images\01node\2022-03-10_190527.png" style="zoom:80%;" />

## 3.1. 区分 LTS 版本和 Current 版本的不同

1.  LTS 为长期稳定版，对于追求稳定性的企业级项目来说，推荐安装 LTS 版本的 Node.js。 
2.  Current 为新特性尝鲜版，对热衷于尝试新特性的用户来说，推荐安装 Current 版本的 Node.js。但是，Current 版本中可 能存在隐藏的 Bug 或安全性漏洞，因此不推荐在企业级项目中使用 Current 版本的 Node.js。

## 3.2查看已安装的 Node.js 的版本号 

1. 打开终端，在终端输入命令 node –v 后，按下回车键，即可查看已安装的 Node.js 的版本号。 
2. Windows 系统快速打开终端的方式： 使用快捷键（Windows徽标键 + R）打开运行面板，输入 cmd 后直接回车，即可打开终端。

## 3.3什么是终端

![](images\01node\2022-03-10_190652.png)

​	终端（英文：Terminal）是专门为开发人员设计的，用 于实现人机交互的一种方式。 作为一名合格的程序员，我们有必要识记一些常用的终端 命令，来辅助我们更好的操作与使用计算机

## 3.4 在 Node.js 环境中执行 JavaScript 代码 

1. 打开终端 
2.  输入 node 要执行的js文件的路径

### 3.4.1 终端中的快捷键 

在 Windows 的 powershell 或 cmd 终端中，我们可以通过如下快捷键，来提高终端的操作效率： 

1.  使用 ↑ 键，可以快速定位到上一次执行的命令 
2. 使用 tab 键，能够快速补全路径 
3.  使用 esc 键，能够快速清空当前已输入的命令 
4.  输入 cls 命令，可以清空终端

# 二、 fs 文件系统模块

# 1 、什么是 fs 文件系统模块

 fs 模块是 Node.js 官方提供的、用来操作文件的模块。它提供了一系列的方法和属性，用来满足用户对文件的操作需求。 例如： 

-  fs.readFile() 方法，用来读取指定文件中的内容 
-  fs.writeFile() 方法，用来向指定的文件中写入内容 如果要在 JavaScript 代码中，使用 fs 模块来操作文件，则需要使用如下的方式先导入它

```js
const fs=require('fs')
```

# 2、 读取指定文件中的内容 

## 2.1fs.readFile() 的语法格式 

使用 fs.readFile() 方法，可以读取指定文件中的内容，语法格式如下：

```js
fs.readFile(path,[,options],callback)
```

参数解读： 

-  参数1：必选参数，字符串，表示文件的路径。 
-  参数2：可选参数，表示以什么编码格式来读取文件。 
-  参数3：必选参数，文件读取完成后，通过回调函数拿到读取的结果

## 2.2fs.readFile() 的示例代码 

以 utf8 的编码格式，读取指定文件的内容，并打印 err 和 dataStr 的值：

```js
const fs = require('fs')//导入fs 文件系统模块
fs.readFile('./files/11.txt', 'utf8', function(err, dataStr) {
  // 2.1 打印失败的结果
  // 如果读取成功，则 err 的值为 null
  // 如果读取失败，则 err 的值为 错误对象，dataStr 的值为 undefined
  console.log(err)
  console.log('-------')
  // 2.2 打印成功的结果
  console.log(dataStr)
})
```

## 2.3判断文件是否读取成功 

可以判断 err 对象是否为 null，从而知晓文件读取的结果：

```js
const fs = require('fs')//导入fs 文件系统模块

fs.readFile('./files/11.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
})
```

# 3、向指定的文件中写入内容 

## 3.1fs.writeFile() 的语法格式

- 使用 fs.writeFile() 方法，可以向指定的文件中写入内容，语法格式如下：

```js
fs.writeFile(path, data[,options],callback) 
```

**参数解读：**

-  参数1：必选参数，需要指定一个文件路径的字符串，表示文件的存放路径。 
-  参数2：必选参数，表示要写入的内容。 
-  参数3：可选参数，表示以什么格式写入文件内容，默认值是 utf8。 
-  参数4：必选参数，文件写入完成后的回调函数。

fs.writeFile() 的示例代码 

- 向指定的文件路径中，写入文件内容：

```JS
const fs = require('fs')//导入fs 文件系统模块
fs.writeFile('./files/3.txt', 'ok123', function(err) {
  //  如果文件写入成功，则 err 的值等于 null
  console.log(err)
})
```

- 判断文件是否写入成功 可以判断 err 对象是否为 null，从而知晓文件写入的结果：

```JS
const fs = require('fs')//导入fs 文件系统模块
fs.writeFile('./files/3.txt', 'ok123', function(err) {
  // 2.1 如果文件写入成功，则 err 的值等于 null
  // 2.2 如果文件写入失败，则 err 的值等于一个 错误对象
  // console.log(err)
  if (err) {
    return console.log('文件写入失败！' + err.message)
  }
  console.log('文件写入成功！')
})
```

## 3.2 练习 - 考试成绩整理

核心实现步骤 

1.  导入需要的 fs 文件系统模块 
2.  使用 fs.readFile() 方法，读取素材目录下的 成绩.txt 文件 
3.  判断文件是否读取失败 
4.  文件读取成功后，处理成绩数据 
5.  将处理完成的成绩数据，调用 fs.writeFile() 方法，写入到新文件 成绩-ok.txt 中

```JS
// 1. 导入 fs 模块
const fs = require('fs')

// 2. 调用 fs.readFile() 读取文件的内容
fs.readFile('../素材/成绩.txt', 'utf8', function(err, dataStr) {
  // 3. 判断是否读取成功
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  // console.log('读取文件成功！' + dataStr)

  // 4.1 先把成绩的数据，按照空格进行分割
  const arrOld = dataStr.split(' ')
  // 4.2 循环分割后的数组，对每一项数据，进行字符串的替换操作
  const arrNew = []
  arrOld.forEach(item => {
    arrNew.push(item.replace('=', '：'))
  })
  // 4.3 把新数组中的每一项，进行合并，得到一个新的字符串
  const newStr = arrNew.join('\r\n')

  // 5. 调用 fs.writeFile() 方法，把处理完毕的成绩，写入到新文件中
  fs.writeFile('./files/成绩-ok.txt', newStr, function(err) {
    if (err) {
      return console.log('写入文件失败！' + err.message)
    }
    console.log('成绩写入成功！')
  })
})
```

# 4、fs 模块 - 路径动态拼接的问题

​	在使用 fs 模块操作文件时，如果提供的操作路径是以 **./ 或 ../ 开头的相对路径时**，**很容易出现路径动态拼接错误的问题**。

- 原因：代码在运行的时候，会以执行 node 命令时所处的目录，动态拼接出被操作文件的完整路径。 
- 解决方案：在使用 fs 模块操作文件时，直接提供完整的路径，不要提供 ./ 或 ../ 开头的相对路径，从而防止路径动态拼接的问题。

```js
const fs = require('fs')
// 出现路径拼接错误的问题，是因为提供了 ./ 或 ../ 开头的相对路径
// 如果要解决这个问题，可以直接提供一个完整的文件存放路径就行
/* fs.readFile('./files/1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
}) */

// 移植性非常差、不利于维护
/* fs.readFile('C:\\Users\\escook\\Desktop\\Node.js基础\\day1\\code\\files\\1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
}) */

// __dirname 表示当前文件所处的目录
// console.log(__dirname)

fs.readFile(__dirname + '/files/1.txt', 'utf8', function(err, dataStr) {
  if (err) {
    return console.log('读取文件失败！' + err.message)
  }
  console.log('读取文件成功！' + dataStr)
})
```

# 三、path 路径模块

# 1、什么是 path 路径模块 

path 模块是 Node.js 官方提供的、用来处理路径的模块。它提供了一系列的方法和属性，用来满足用户对路径的处理 需求。 例如： 

- path.join() 方法，用来将多个路径片段拼接成一个完整的路径字符串 
-  path.basename() 方法，用来从路径字符串中，将文件名解析出来 如果要在 JavaScript 代码中，使用 path 模块来处理路径，则需要使用如下的方式先导入它：

```js
const path = require('path')//导入path 路径模块 
```

# 2、 路径拼接

## 2.1path.join() 的语法格式 

使用 path.join() 方法，可以把多个路径片段拼接为完整的路径字符串，语法格式如下：

```js
fs.readFile([...paths])
```

参数解读： 

-  ...paths  路径片段的序列 
-  返回值: string

## 2.2path.join() 的代码示例 

使用 path.join() 方法，可以把多个路径片段拼接为完整的路径字符串：

```js
const path = require('path')//导入path 路径模块 
const fs = require('fs')

const pathStr = path.join('/a', '/b/c', '../../', './d', 'e')
console.log(pathStr)  // 输出\a\b\d\e

// fs.readFile(__dirname + '/files/1.txt')

fs.readFile(path.join(__dirname, './files/1.txt'), 'utf8', function(err, dataStr) {
  if (err) {
    return console.log(err.message)
  }
  console.log(dataStr)
})
```

**注意**：今后凡是涉及到路径拼接的操作，都要使用 path.join() 方法进行处理。不要直接使用 + 进行字符串的拼接。

# 3、获取路径中的文件名

## 3.1path.basename() 的代码示例

 使用 path.basename() 方法，可以从一个文件路径中，获取到文件的名称部分：

```js
const path = require('path')

// 定义文件的存放路径
const fpath = '/a/b/c/index.html'

const fullName = path.basename(fpath)
console.log(fullName)//index.html

const nameWithoutExt = path.basename(fpath, '.html')
console.log(nameWithoutExt)//index
```

# 4、获取路径中的文件扩展名

## 4.1path.extname() 的语法格式

 使用 path.extname() 方法，可以获取路径中的扩展名部分，语法格式如下：

```js
path.extname(path)
```

**参数解读：** 

-  path 必选参数，表示一个路径的字符串 
-  返回:  返回得到的扩展名字符串

## 4.2path.extname() 的代码示例 

使用 path.extname() 方法，可以获取路径中的扩展名部分：

```js
const path = require('path')
// 这是文件的存放路径
const fpath = '/a/b/c/index.html'

const fext = path.extname(fpath)
console.log(fext)//.html
```

# 5、综合案例 - 时钟案例

案例的实现步骤 

1.  创建两个正则表达式，分别用来匹配 
2. 使用 fs 模块，读取需要被处理的 HTML 文件
3. 自定义 resolveCSS 方法，来写入 index.css 样式文件
4. 自定义 resolveJS 方法，来写入 index.js 脚本文件
5. 自定义 resolveJS 方法，来写入 index.js 脚本文件

```js
// 1.1 导入 fs 模块
const fs = require('fs')
// 1.2 导入 path 模块
const path = require('path')
// 1.3 定义正则表达式，分别匹配 <style></style> 和 <script></script> 标签
const regStyle = /<style>[\s\S]*<\/style>/
const regScript = /<script>[\s\S]*<\/script>/
// 2.1 调用 fs.readFile() 方法读取文件
fs.readFile(path.join(__dirname, '../素材/index.html'), 'utf8', function(err, dataStr) {
  // 2.2 读取 HTML 文件失败
  if (err) return console.log('读取HTML文件失败！' + err.message)
  // 2.3 读取文件成功后，调用对应的三个方法，分别拆解出 css, js, html 文件
  resolveCSS(dataStr)
  resolveJS(dataStr)
  resolveHTML(dataStr)
})
// 3.1 定义处理 css 样式的方法
function resolveCSS(htmlStr) {
  // 3.2 使用正则提取需要的内容
  const r1 = regStyle.exec(htmlStr)
  // 3.3 将提取出来的样式字符串，进行字符串的 replace 替换操作
  const newCSS = r1[0].replace('<style>', '').replace('</style>', '')
  // 3.4 调用 fs.writeFile() 方法，将提取的样式，写入到 clock 目录中 index.css 的文件里面
  fs.writeFile(path.join(__dirname, './clock/index.css'), newCSS, function(err) {
    if (err) return console.log('写入 CSS 样式失败！' + err.message)
    console.log('写入样式文件成功！')
  })
}
// 4.1 定义处理 js 脚本的方法
function resolveJS(htmlStr) {
  // 4.2 通过正则，提取对应的 <script></script> 标签内容
  const r2 = regScript.exec(htmlStr)
  // 4.3 将提取出来的内容，做进一步的处理
  const newJS = r2[0].replace('<script>', '').replace('</script>', '')
  // 4.4 将处理的结果，写入到 clock 目录中的 index.js 文件里面
  fs.writeFile(path.join(__dirname, './clock/index.js'), newJS, function(err) {
    if (err) return console.log('写入 JavaScript 脚本失败！' + err.message)
    console.log('写入 JS 脚本成功！')
  })
}
// 5.1 定义处理 HTML 结构的方法
function resolveHTML(htmlStr) {
  // 5.2 将字符串调用 replace 方法，把内嵌的 style 和 script 标签，替换为外联的 link 和 script 标签
  const newHTML = htmlStr.replace(regStyle, '<link rel="stylesheet" href="./index.css" />').replace(regScript, '<script src="./index.js"></script>')
  // 5.3 写入 index.html 这个文件
  fs.writeFile(path.join(__dirname, './clock/index.html'), newHTML, function(err) {
    if (err) return console.log('写入 HTML 文件失败！' + err.message)
    console.log('写入 HTML 页面成功！')
  })
}
```

**案例的两个注意点**

1.  fs.writeFile() 方法只能用来创建文件，不能用来创建路径 
2.  重复调用 fs.writeFile() 写入同一个文件，新写入的内容会覆盖之前的旧内容

# 四、http 模块

#  1、什么是 http 模块 

回顾：什么是客户端、什么是服务器？

​	 在网络节点中，负责消费资源的电脑，叫做客户端；负责对外提供网络资源的电脑，叫做服务器。

​	 http 模块是 Node.js 官方提供的、用来创建 web 服务器的模块。通过 http 模块提供的 http.createServer() 方法，就 能方便的把一台普通的电脑，变成一台 Web 服务器，从而对外提供 Web 资源服务。 如果要希望使用 http 模块创建 Web 服务器，则需要先导入它：

## 4.2 进一步理解 http 模块的作用 

​	服务器和普通电脑的区别在于，服务器上安装了 web 服务器软件，例如：IIS、Apache 等。通过安装这些服务器软件， 就能把一台普通的电脑变成一台 web 服务器。 在 Node.js 中，我们不需要使用 IIS、Apache 等这些第三方 web 服务器软件。因为我们可以基于 Node.js 提供的 http 模块，通过几行简单的代码，就能轻松的手写一个服务器软件，从而对外提供 web 服务。

## 4.3 服务器相关的概念 

### 4.3.1IP 地址

 IP 地址就是互联网上每台计算机的唯一地址，因此 IP 地址具有唯一性。如果把“个人电脑”比作“一台电话”，那么“IP地 址”就相当于“电话号码”，只有在知道对方 IP 地址的前提下，才能与对应的电脑之间进行数据通信。

 IP 地址的格式：通常用“点分十进制”表示成（a.b.c.d）的形式，其中，a,b,c,d 都是 0~255 之间的十进制整数。例如：用 点分十进表示的 IP地址（192.168.1.1） 

**注意：** 

-  互联网中每台 Web 服务器，都有自己的 IP 地址，例如：大家可以在 Windows 的终端中运行 ping www.baidu.com 命 令，即可查看到百度服务器的 IP 地址。 
-  在开发期间，自己的电脑既是一台服务器，也是一个客户端，为了方便测试，可以在自己的浏览器中输入 127.0.0.1 这个 IP 地址，就能把自己的电脑当做一台服务器进行访问了。

### 4.3.2域名和域名服务器

​	尽管 IP 地址能够唯一地标记网络上的计算机，但IP地址是一长串数字，不直观，而且不便于记忆，于是人们又发明了另一套
字符型的地址方案，即所谓的域名（Domain Name）地址。
​	IP地址和域名是一一对应的关系，这份对应关系存放在一种叫做域名服务器(DNS，Domain name server)的电脑中。使用者
只需通过好记的域名访问对应的服务器即可，对应的转换工作由域名服务器实现。因此，域名服务器就是提供 IP 地址和域名
之间的转换服务的服务器。
注意：

-  单纯使用 IP 地址，互联网中的电脑也能够正常工作。但是有了域名的加持，能让互联网的世界变得更加方便。
-  在开发测试期间， 127.0.0.1 对应的域名是 localhost，它们都代表我们自己的这台电脑，在使用效果上没有任何区别

### 4.3.3服务器相关的概念

​	计算机中的端口号，就好像是现实生活中的门牌号一样。通过门牌号，外卖小哥可以在整栋大楼众多的房间中，准确把外卖 送到你的手中。

​	 同样的道理，在一台电脑中，可以运行成百上千个 web 服务。每个 web 服务都对应一个唯一的端口号。客户端发送过来的 网络请求，通过端口号，可以被准确地交给对应的 web 服务进行处理。

<img src="images\01node\2022-03-10_195929.png" style="zoom:80%;" />

**注意**： 

1.  每个端口号不能同时被多个 web 服务占用。 
2.  在实际应用中，URL 中的 80 端口可以被省略。

# 2 创建最基本的 web 服务器 

## 2.1创建 web 服务器的基本步骤 

1.  导入 http 模块 
2.  创建 web 服务器实例
3. 为服务器实例绑定 request 事件，监听客户端的请求 
4.  启动服务器

**步骤1 - 导入 http 模块**

 如果希望在自己的电脑上创建一个 web 服务器，从而对外提供 web 服务，则需要导入 http 模块：

```js
const http = require('http')
```

 **步骤2 - 创建 web 服务器实例**

调用 http.createServer() 方法，即可快速创建一个 web 服务器实例：

```js
// 2. 创建 web 服务器实例
const server = http.createServer()
```

**步骤3 - 为服务器实例绑定 request 事件**

为服务器实例绑定 request 事件，即可监听客户端发送过来的网络请求：

```js
server.on('request', function (req, res) {
  console.log('Someone visit our web server.')
})
```

**步骤4 - 启动服务器**

调用服务器实例的 .listen() 方法，即可启动当前的 web 服务器实例：

```js
server.listen(8080, function () {  
  console.log('server running at http://127.0.0.1:8080')
})
```

## 2.2 req 请求对象、res 响应对象 

​	只要服务器接收到了客户端的请求，就会调用通过 **server.on() 为服务器绑定的 request 事件处理函数**。 如果想在事件处理函数中，访问与**客户端相关的数据或属**，

​	在服务器的 request 事件处理函数中，如果想访问与**服务器相关**的**数据或属性**可以使用如下的方式

```js
const http = require('http')
const server = http.createServer()
// req 是请求对象，包含了与客户端相关的数据和属性
server.on('request', (req, res) => {
  // req.url 是客户端请求的 URL 地址
  const url = req.url
  // req.method 是客户端请求的 method 类型
  const method = req.method
  const str = `Your request url is ${url}, and request method is ${method}`
  console.log(str)
  // 调用 res.end() 方法，向客户端响应一些内容
  res.end(str)
})
server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})

```

## 2.3解决中文乱码问题

 当调用 res.end() 方法，向客户端发送中文内容的时候，会出现乱码问题，此时，需要手动设置内容的编码格式

```js
const http = require('http')
const server = http.createServer()

server.on('request', (req, res) => {
  // 定义一个字符串，包含中文的内容
  const str = `您请求的 URL 地址是 ${req.url}，请求的 method 类型为 ${req.method}`
  // 调用 res.setHeader() 方法，设置 Content-Type 响应头，解决中文乱码的问题
  res.setHeader('Content-Type', 'text/html; charset=utf-8')
  // res.end() 将内容响应给客户端
  res.end(str)
})

server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})

```

## 2.4根据不同的 url 响应不同的 html 内容

### 2.4.1核心实现步骤 

1.  获取请求的 url 地址 
2.  设置默认的响应内容为 404 Not found 
3.  判断用户请求的是否为 / 或 /index.html 首页 
4.  判断用户请求的是否为 /about.html 关于页面 
5.  设置 Content-Type 响应头，防止中文乱码 
6.  使用 res.end() 把内容响应给客户端

### 2.4.2动态响应内容

```js
const http = require('http')
const server = http.createServer()

server.on('request', (req, res) => {
  // 1. 获取请求的 url 地址
  const url = req.url
  // 2. 设置默认的响应内容为 404 Not found
  let content = '<h1>404 Not found!</h1>'
  // 3. 判断用户请求的是否为 / 或 /index.html 首页
  // 4. 判断用户请求的是否为 /about.html 关于页面
  if (url === '/' || url === '/index.html') {
    content = '<h1>首页</h1>'
  } else if (url === '/about.html') {
    content = '<h1>关于页面</h1>'
  }
  // 5. 设置 Content-Type 响应头，防止中文乱码
  res.setHeader('Content-Type', 'text/html; charset=utf-8')
  // 6. 使用 res.end() 把内容响应给客户端
  res.end(content)
})

server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})
```

# 3、案例 - 实现 clock 时钟的 web 服务器

## 3.1核心思路 

把文件的实际存放路径，作为每个资源的请求 url 地址。

## 3.2实现步骤

1.   导入需要的模块
2.  创建基本的 web 服务器 
3.  将资源的请求 url 地址映射为文件的存放路径
4.  读取文件内容并响应给客户端 
5.  优化资源的请求路径

```js
// 1.1 导入 http 模块
const http = require('http')
// 1.2 导入 fs 模块
const fs = require('fs')
// 1.3 导入 path 模块
const path = require('path')
// 2.1 创建 web 服务器
const server = http.createServer()
// 2.2 监听 web 服务器的 request 事件
server.on('request', (req, res) => {
  // 3.1 获取到客户端请求的 URL 地址
  //     /clock/index.html
  //     /clock/index.css
  //     /clock/index.js
  const url = req.url
  // 3.2 把请求的 URL 地址映射为具体文件的存放路径
  // const fpath = path.join(__dirname, url)
  // 5.1 预定义一个空白的文件存放路径
  let fpath = ''
  if (url === '/') {
    fpath = path.join(__dirname, './clock/index.html')
  } else {
    //     /index.html
    //     /index.css
    //     /index.js
    fpath = path.join(__dirname, '/clock', url)
  }
  // 4.1 根据“映射”过来的文件路径读取文件的内容
  fs.readFile(fpath, 'utf8', (err, dataStr) => {
    // 4.2 读取失败，向客户端响应固定的“错误消息”
    if (err) return res.end('404 Not found.')
    // 4.3 读取成功，将读取成功的内容，响应给客户端
    res.end(dataStr)
  })
})
// 2.3 启动服务器
server.listen(80, () => {
  console.log('server running at http://127.0.0.1')
})
```

# 五、**模块化**

能够说出模块化的好处

能够知道 CommonJS 规定了哪些内容

能够说出 Node.js 中模块的三大分类各自是什么

能够使用 npm 管理包

能够了解什么是规范的包结构

能够了解模块的加载机制

# 1、**模块化的基本概念**

## 1.1什么是模块化

​	**模块化**是指解决一个复杂问题时，自顶向下逐层把系统划分成若干模块的过程。对于整个系统来说，模块是可组合、分解和更换的单元。

## 1.2**现实生活中的模块化**

<img src="images\01node\2022-03-10_203842.png" style="zoom:80%;" />

## 1.3**编程领域中的模块化**

编程领域中的模块化，就是**遵守固定的规则**，把一个大文件拆成独立并互相依赖的多个小模块。

把代码进行模块化拆分的好处：

1. 提高了代码的复用性
2. 提高了代码的可维护性
3. 可以实现按需加载

## 1.4模块化规范

**模块化规范**就是对代码进行模块化的拆分与组合时，需要遵守的那些规则。

例如：

- 使用什么样的语法格式来引用模块
- 在模块中使用什么样的语法格式向外暴露成员

**模块化规范的好处**：大家都遵守同样的模块化规范写代码，降低了沟通的成本，极大方便了各个模块之间的相互调用，利人利己。

# 2、Node.js 中的模块化

## 2.1Node.js 中模块的分类

Node.js 中根据模块来源的不同，将模块分为了 3 大类，分别是：

1.  内置模块（内置模块是由 Node.js 官方提供的，例如 fs、path、http 等）
2. 自定义模块（用户创建的每个 .js 文件，都是自定义模块）
3.  第三方模块（由第三方开发出来的模块，并非官方提供的内置模块，也不是用户创建的自定义模块，使用前需要先下载）

## 2.2加载模块

使用强大的 require() 方法，可以加载需要的内置模块、用户自定义模块、第三方模块进行使用。例如：

```js
 //1．加载内置的fs模块
 const fs = require( 'fs ')3
 //2．加载用户的自定义模块
 const custom = require( ' ./ custom.js ")6
 //3．加载第三方模块(关于第三方模块的下载和使用，会在后面的课程中进行专门的讲解)
 const moment = require( " moment" )
```

注意：使用 require() 方法加载其它模块时，会执行被加载模块中的代码。

## 2.3Node.js 中的模块作用域

### 2.3.1**什么是模块作用域**

和函数作用域类似，在自定义模块中定义的变量、方法等成员，只能在当前模块内被访问，这种模块级别的访问限制，叫做**模块作用域**。

<img src="images\01node\2022-03-10_204519.png" style="zoom: 80%;" />

### 2.3.2**模块作用域的**好处

防止了全局变量污染的问题

<img src="images\01node\2022-03-10_204645.png" style="zoom:80%;" />

# 3、向外共享模块作用域中的成员

## 3.2**module** **对象**

在每个 .js 自定义模块中都有一个 module 对象，它里面存储了和当前模块有关的信息，打印如下：

<img src="images\01node\2022-03-10_204750.png" style="zoom:80%;" />

## 3.3**module.exports** **对象**

在自定义模块中，可以使用 module.exports 对象，将模块内的成员共享出去，供外界使用。

外界用 require() 方法导入自定义模块时，得到的就是 module.exports 所指向的对象。

## 3.4**共享成员时的**注意点

使用 require() 方法导入模块时，导入的结果，**永远以** **module.exports** **指向的对象为准**。

<img src="images\01node\2022-03-10_205008.png" style="zoom:80%;" />

## 3.5**exports** **对象**

​	由于 module.exports 单词写起来比较复杂，为了简化向外共享成员的代码，Node 提供了 exports 对象。默认情况下，exports 和 module.exports 指向同一个对象。**最终共享的结果，还是以 module.exports 指向的对象为准。**

<img src="images\01node\2022-03-10_205212.png" style="zoom:80%;" />

## **3.6exports** **和** **module.exports** **的使用误区**

时刻谨记，require() 模块时，得到的永远是 module.exports 指向的对象：

<img src="images\01node\2022-03-10_205444.png" style="zoom:80%;" />

**注意：**为了防止混乱，建议大家不要在同一个模块中同时使用 exports 和 module.exports

## 3.7Node.js 中的模块化规范

Node.js 遵循了 CommonJS 模块化规范，CommonJS 规定了模块的特性和各模块之间如何相互依赖。

**CommonJS 规定：**

1. 每个模块内部，module 变量代表当前模块。
2. module 变量是一个对象，它的 exports 属性（即 module.exports）是对外的接口。
3. 加载某个模块，其实是加载该模块的 module.exports 属性。require() 方法用于加载模块。

# 4、npm与包

## 1、包

### 1.1**什么是包**

Node.js 中的第三方模块又叫做包。就像电脑和计算机指的是相同的东西，第三方模块和包指的是同一个概念，只不过叫法不同。

### 1.2**包的来源**

不同于 Node.js 中的内置模块与自定义模块，包是由第三方个人或团队开发出来的，免费供所有人使用。

**注意**：Node.js 中的包都是免费且开源的，不需要付费即可免费下载使用。

### 1.3**为什么需要包**

- 由于 Node.js 的内置模块仅提供了一些底层的 API，导致在基于内置模块进行项目开发的时，效率很低。

- 包是基于内置模块封装出来的，提供了更高级、更方便的 API，极大的提高了开发效率。

- 包和内置模块之间的关系，类似于 jQuery 和 浏览器内置 API 之间的关系。

### 1.4**从哪里下载包**

​	国外有一家 IT 公司，叫做 **npm, Inc.** 这家公司旗下有一个非常著名的网站： https://www.npmjs.com/ ，它是**全球最大的包共享平台**，你可以从这个网站上搜索到任何你需要的包，只要你有足够的耐心！

​	到目前位置，全球约 1100 多万的开发人员，通过这个包共享平台，开发并共享了超过 120 多万个包 供我们使用。

​	**npm, Inc.** **公司**提供了一个地址为 https://registry.npmjs.org/ 的服务器，来对外共享所有的包，我们可以从这个服务器上下载自己所需要的包。

**注意：**

1. 从 https://www.npmjs.com/ 网站上搜索自己所需要的包
2. 从 https://registry.npmjs.org/ 服务器上下载自己需要的包

### 1.5**如何下载包**

​	**npm, Inc.** **公司**提供了一个包管理工具，我们可以使用这个包管理工具，从 https://registry.npmjs.org/ 服务器把需要的包下载到本地使用。

​	这个包管理工具的名字叫做 Node Package Manager（简称 npm 包管理工具），这个包管理工具随着 Node.js 的安装包一起被安装到了用户的电脑上。

大家可以在终端中执行 **npm -v** 命令，来查看自己电脑上所安装的 npm 包管理工具的版本号：

<img src="images\01node\2022-03-10_205925.png" style="zoom:80%;" />

# 2、npm 初体验

## 2.1**格式化时间的传统做法**

1. 创建格式化时间的自定义模块

2. 定义格式化时间的方法

3. 创建补零函数

4. 从自定义模块中导出格式化时间的函数

5. 导入格式化时间的自定义模块

6. 调用格式化时间的函数

   <img src="images\01node\2022-03-10_210252.png" style="zoom:80%;" />

## 2.3**格式化时间的高级做法**

1. 使用 npm 包管理工具，在项目中安装格式化时间的包 moment
2. 使用 require() 导入格式化时间的包
3. 参考 moment 的官方 API 文档对时间进行格式化

```js
// 1. 导入需要的包
// 注意：导入的名称，就是装包时候的名称
const moment = require('moment')

const dt = moment().format('YYYY-MM-DD HH:mm:ss')
console.log(dt)
```

## 2.4**在项目中安装包的命令**

如果想在项目中安装指定名称的包，需要运行如下的命令

```js
npm install 包的完整名称
```

上述的装包命令，可以简写成如下格式：

```
npm i 包的完整名称
```

## 2.4**初次装包后多了哪些文件**

初次装包完成后，在项目文件夹下多一个叫做 node_modules 的文件夹和 package-lock.json 的配置文件。其中：

- node_modules 文件夹用来存放所有已安装到项目中的包。require() 导入第三方包时，就是从这个目录中查找并加载包。
- package-lock.json 配置文件用来记录 node_modules 目录下的每一个包的下载信息，例如包的名字、版本号、下载地址等。

**注意：**程序员不要手动修改 node_modules 或 package-lock.json 文件中的任何代码，npm 包管理工具会自动维护它们。

## 2.5**安装指定版本的包**

默认情况下，使用 npm install 命令安装包的时候，会自动安装最新版本的包。如果需要安装指定版本的包，可以在包名之后，通过 @ 符号指定具体的版本，例如：

```js
npm i 包的完整名称@2.2.2
```

## 2.6**包的语义化版本规范**

包的版本号是以“点分十进制”形式进行定义的，总共有三位数字，例如 **2.24.0**

其中每一位数字所代表的的含义如下：

- 第1位数字：大版本
- 第2位数字：功能版本
- 第3位数字：Bug修复版本

**版本号提升的规则**：只要前面的版本号增长了，则后面的版本号归零。

## 2.7包管理配置文件

npm 规定，在项目根目录中，**必须**提供一个叫做 package.json 的包管理配置文件。用来记录与项目有关的一些配置信息。例如：

- 项目的名称、版本号、描述等
- 项目中都用到了哪些包
- 哪些包只在开发期间会用到
- l那些包在开发和部署时都需要用到

### 2.7.1**多人协作的问题**

<img src="images\01node\图片1.png" style="zoom:80%;" />

- 整个项目的体积是 30.4M
- 第三方包的体积是 28.8M
- 项目源代码的体积 1.6M

**遇到的问题：**第三方包的体积过大，不方便团队成员之间共享项目源代码。

**解决方案：**共享时剔除node_modules

### 2.7.2**如何记录项目中安装了哪些包**

​	在项目根目录中，创建一个叫做 package.json 的配置文件，即可用来记录项目中安装了哪些包。从而方便剔除 node_modules 目录之后，在团队成员之间共享项目的源代码。

**注意**：**今后在项目开发中，一定要把 node_modules 文件夹，添加到 .gitignore 忽略文件中。**

### 2.7.3**快速创建** **package.json**

npm 包管理工具提供了一个快捷命令，可以在执行命令时所处的目录中，快速创建 package.json 这个包管理配置文件：

```
npm init -y
```

注意：

1. 上述命令只能在英文的目录下成功运行！所以，项目文件夹的名称一定要使用英文命名，不要使用中文，不能出现空格。
2. 运行 npm install 命令安装包的时候，npm 包管理工具会自动把包的名称和版本号，记录到 package.json 中。

### 2.7.4**dependencies** **节点**

package.json 文件中，有一个 dependencies 节点，专门用来记录您使用 npm install 命令安装了哪些包。

<img src="images\01node\2022-03-10_211909.png" style="zoom:80%;" />

### 2.7.5**一次性安装所有的包**

当我们拿到一个剔除了 node_modules 的项目之后，需要先把所有的包下载到项目中，才能将项目运行起来。

否则会报类似于下面的错误：

<img src="images\01node\2022-03-10_212011.png" style="zoom:80%;" />

可以运行 npm install 命令（或 npm i）一次性安装所有的依赖包：

<img src="images\01node\2022-03-10_212052.png" style="zoom:80%;" />

可以运行 npm uninstall 命令，来卸载指定的包：

```
 npm uninstall 包名
```

**注意：npm uninstall 命令执行成功后，会把卸载的包，自动从 package.json 的 dependencies 中移除掉。**

### **2.7.6**devDependencies **节点**

​	如果某些包**只在项目开发阶段**会用到，在**项目上线之后不会用到**，则建议把这些包记录到 devDependencies 节点中。与之对应的，如果某些包在开发和项目上线之后都需要用到，则建议把这些包记录到 dependencies 节点中。您可以使用如下的命令，将包记录到 devDependencies 节点中：

```js
//安装指定的包，并记录到devDependencies 节点中
npmi 包名 -D
//注意:上述命令是简写形式，等价于下面完整的写法:
npm install 包名 --save-dev
```

## 2.8**解决下包速度慢的问题**

### 2.8.1**为什么下包速度慢**

​	在使用 npm 下包的时候，默认从国外的 https://registry.npmjs.org/ 服务器进行下载，此时，网络数据的传输需要经过漫长的海底光缆，因此下包速度会很慢。

扩展阅读 - 海底光缆：

- [https://baike.baidu.com/item/%E6%B5%B7%E5%BA%95%E5%85%89%E7%BC%86/4107830](https://baike.baidu.com/item/海底光缆/4107830)
- [https://baike.baidu.com/item/%E4%B8%AD%E7%BE%8E%E6%B5%B7%E5%BA%95%E5%85%89%E7%BC%86/10520363](https://baike.baidu.com/item/中美海底光缆/10520363)
- https://baike.baidu.com/item/APG/23647721?fr=aladdin

### 2.8.2 **淘宝** **NPM** **镜像服务器**

​	淘宝在国内搭建了一个服务器，专门把国外官方服务器上的包同步到国内的服务器，然后在国内提供下包的服务。从而极大的提高了下包的速度。

**扩展**：**镜像**（Mirroring）是一种文件存储形式，一个磁盘上的数据在另一个磁盘上存在一个完全相同的副本即为镜像。

<img src="images\01node\2022-03-10_212742.png" style="zoom:80%;" />

### 2.8.3**切换** **npm** **的下包镜像源**

下包的镜像源，指的就是下包的服务器地址。

```js
//查看当前的下包镜像源
npm config get registry
//将下包的镜像源切换为淘宝镜像源
npm config set registry=https ://registry .npm. taobao.org/
//检查镜像源是否下载成功
npm config get registry
```

### 2.8.4**nrm**

为了更方便的切换下包的镜像源，我们可以安装 **nrm** 这个小工具，利用 nrm 提供的终端命令，可以快速查看和切换下包的镜像源。

```js
//通过npm包管理器，将nrm安装为全局可用的工具
npminrm-g
//查看所有可用的镜像源
nrm ls
//将下包的镜像源切换为taobao镜像
nrm use taobao
```

## 2.9包的分类

使用 npm 包管理工具下载的包，共分为两大类，分别是：

- 项目包
- 全局包

### 2.9.1**项目包**

那些被安装到项目的 node_modules 目录中的包，都是项目包。

项目包又分为两类，分别是：

- 开发依赖包（被记录到 devDependencies 节点中的包，只在开发期间会用到）
- 核心依赖包（被记录到 dependencies 节点中的包，在开发期间和项目上线之后都会用到）

```js
1npmi 包名 -D //开发依赖包(会被记录到devDependencies 节点F)
npmi  包名 //核心依赖包(会被记录到dependencies 节点下)

```

### 2.9.2**全局包**

在执行 npm install 命令时，如果提供了 -g 参数，则会把包安装为全局包。

全局包会被安装到 C:\Users\用户目录\AppData\Roaming\npm\node_modules 目录下。

```js
npm i 包名 -g //全局安装指定的包
npm uninstall 包名 -g //卸载全局安装的包
```

注意：

1. **只有工具性质的包，才有全局安装的必要性**。因为它们提供了好用的终端命令。
2. 判断某个包是否需要全局安装后才能使用，可以参考官方提供的使用说明即可。

### **2.9.3 i5ting_toc**

i5ting_toc 是一个可以把 md 文档转为 html 页面的小工具，使用步骤如下：

```js
//将i5ting toc安装为全局包
npm install -g i5ting toc
//调用i5ting toc, 轻松实现md转html 的功能
i5ting toc -f 要转换的md文件路径 -0 
```

#### 2.10规范的包结构

在清楚了包的概念、以及如何下载和使用包之后，接下来，我们深入了解一下包的内部结构。

一个规范的包，它的组成结构，必须符合以下 3 点要求：

1. 包必须以单独的目录而存在
2. 包的顶级目录下要必须包含 package.json 这个包管理配置文件
3. package.json 中必须包含 name，version，main 这三个属性，分别代表包的名字、版本号、包的入口。

**注意：以上 3 点要求是一个规范的包结构必须遵守的格式，关于更多的约束，可以参考如下网址：**

https://yarnpkg.com/zh-Hans/docs/package-json

#### 2.11开发属于自己的包

- **需要实现的功能**

1. 格式化日期
2. 转义 HTML 中的特殊字符
3. 还原 HTML 中的特殊字符

```js
const itheima = require('./itheima-tools')

// 格式化时间的功能
const dtStr = itheima.dateFormat(new Date())
console.log(dtStr)
console.log('-----------')

// 还原HTML中的特殊字符的功能
const htmlStr = '<h1 title="abc">这是h1标签<span>123&nbsp;</span></h1>'
const str = itheima.htmlEscape(htmlStr)
console.log(str)
console.log('-----------')

const str2 = itheima.htmlUnEscape(str)
console.log(str2)

```

- **初始化包的基本结构**

①新建 itheima-tools 文件夹，作为包的根目录

②在 itheima-tools 文件夹中，新建如下三个文件：

1. lpackage.json （包管理配置文件）
2. lindex.js     （包的入口文件）
3. lREADME.md （包的说明文档）

- **初始化** **package.json**

```json
{
  "name": "itheima-tools",
  "version": "1.1.0",
  "main": "index.js",
  "description": "提供了格式化时间、HTMLEscape相关的功能",
  "keywords": [
    "itheima",
    "dateFormat",
    "escape"
  ],
  "license": "ISC"
}
```

**关于更多 license 许可协议相关的内容**，可参考 https://www.jianshu.com/p/86251523e898

- **在** **index.js** **中定义格式化时间的方法**

```js
// 定义格式化时间的函数
function dateFormat(dateStr) {
  const dt = new Date(dateStr)

  const y = dt.getFullYear()
  const m = padZero(dt.getMonth() + 1)
  const d = padZero(dt.getDate())

  const hh = padZero(dt.getHours())
  const mm = padZero(dt.getMinutes())
  const ss = padZero(dt.getSeconds())

  return `${y}-${m}-${d} ${hh}:${mm}:${ss}`
}

// 定义一个补零的函数
function padZero(n) {
  return n > 9 ? n : '0' + n
}

module.exports = {
  dateFormat
}
```

- **在** **index.js** **中定义转义** **HTML** **的方法**

```js
// 定义转义 HTML 字符的函数
function htmlEscape(htmlstr) {
  return htmlstr.replace(/<|>|"|&/g, match => {
    switch (match) {
      case '<':
        return '&lt;'
      case '>':
        return '&gt;'
      case '"':
        return '&quot;'
      case '&':
        return '&amp;'
    }
  })
}

// 定义还原 HTML 字符串的函数
function htmlUnEscape(str) {
  return str.replace(/&lt;|&gt;|&quot;|&amp;/g, match => {
    switch (match) {
      case '&lt;':
        return '<'
      case '&gt;':
        return '>'
      case '&quot;':
        return '"'
      case '&amp;':
        return '&'
    }
  })
}
module.exports = {
  htmlEscape,
  htmlUnEscape
}

```

- **将不同的功能进行模块化拆分**

1. 将格式化时间的功能，拆分到 src -> dateFormat.js 中
2. 将处理 HTML 字符串的功能，拆分到 src -> htmlEscape.js 中
3. 在 index.js 中，导入两个模块，得到需要向外共享的方法
4. 在 index.js 中，使用 module.exports 把对应的方法共享出去

- **编写包的说明文档**

包根目录中的 README.md 文件，是包的使用说明文档。通过它，我们可以事先把包的使用说明，以 markdown 的格式写出来，方便用户参考。

README 文件中具体写什么内容，没有强制性的要求；只要能够清晰地把包的作用、用法、注意事项等描述清楚即可。

我们所创建的这个包的 README.md 文档中，会包含以下 6 项内容：

安装方式、导入方式、格式化时间、转义 HTML 中的特殊字符、还原 HTML 中的特殊字符、开源协议

#### 2.12发布包

- **注册** **npm** **账号**

1. 访问 https://www.npmjs.com/ 网站，点击 sign up 按钮，进入注册用户界面
2. 填写账号相关的信息：Full Name、Public Email、Username、Password
3. 点击 Create an Account 按钮，注册账号
4. 登录邮箱，点击验证链接，进行账号的验证

- **登录** **npm** **账号**

npm 账号注册完成后，可以在终端中执行 npm login 命令，依次输入用户名、密码、邮箱后，即可登录成功。

<img src="images\01node\2022-03-10_215034.png" style="zoom:80%;" />

注意：在运行 npm login 命令之前，必须先把下包的服务器地址切换为 npm 的官方服务器。否则会导致发布包失败！

- **把包发布到** **npm** **上**

将终端切换到包的根目录之后，运行 npm publish 命令，即可将包发布到 npm 上（注意：包名不能雷同）。

<img src="images\01node\2022-03-10_215131.png" style="zoom:80%;" />

#### 2.14**删除已发布的包**

运行 **npm unpublish 包名 --force 命令**，即可从 npm 删除已发布的包。

![](images\01node\2022-03-12_190651.png)

**注意：**

1. npm unpublish 命令只能删除 72 小时以内发布的包
2. npm unpublish 删除的包，在 24 小时内不允许重复发布
3. 发布包的时候要慎重，尽量不要往 npm 上发布没有意义的包！

# 3、模块的加载机制

## 3.1优先从缓存中加载

**模块在第一次加载后会被缓存**。 这也意味着多次调用 **require()** 不会导致模块的代码被执行多次。

注意：不论是内置模块、用户自定义模块、还是第三方模块，它们都会优先从缓存中加载，从而提高模块的加载效率。

## 3.2内置模块的加载机制

内置模块是由 Node.js 官方提供的模块，内置模块的加载优先级最高。

例如，require('fs') 始终返回内置的 fs 模块，即使在 node_modules 目录下有名字相同的包也叫做 fs。

## 3.3自定义模块的加载机制

​	使用 require() 加载自定义模块时，必须指定以 ./ 或 ../ 开头的路径标识符。在加载自定义模块时，如果没有指定 ./ 或 ../ 这样的路径标识符，则 node 会把它当作内置模块或第三方模块进行加载。

同时，在使用 require() 导入自定义模块时，如果省略了文件的扩展名，则 Node.js 会按顺序分别尝试加载以下的文件：

1. 按照确切的文件名进行加载
2. 补全 .js 扩展名进行加载
3. 补全 .json 扩展名进行加载
4. 补全 .node 扩展名进行加载
5. 加载失败，终端报错

## 3.4第三方模块的加载机制

​	如果传递给 require() 的模块标识符不是一个内置模块，也没有以 ‘./’ 或 ‘../’ 开头，则 Node.js 会从当前模块的父目录开始，尝试从 /node_modules 文件夹中加载第三方模块。

如果没有找到对应的第三方模块，则移动到再上一层父目录中，进行加载，直到文件系统的根目录。

例如，假设在 'C:\Users\itheima\project\foo.js' 文件里调用了 require('tools')，则 Node.js 会按以下顺序查找：

1. C:\Users\itheima\project\node_modules\tools
2.  C:\Users\itheima\node_modules\tools
3.  C:\Users\node_modules\tools
4.  C:\node_modules\tools

## 3.5目录作为模块

当把目录作为模块标识符，传递给 require() 进行加载的时候，有三种加载方式：

1. 在被加载的目录下查找一个叫做 package.json 的文件，并寻找 main 属性，作为 require() 加载的入口
2. 如果目录里没有 package.json 文件，或者 main 入口不存在或无法解析，则 Node.js 将会试图加载目录下的 index.js 文件。
3. 如果以上两步都失败了，则 Node.js 会在终端打印错误消息，报告模块的缺失：Error: Cannot find module 'xxx'

# 六、**Express**

# 1.目标

1. 能够使用 express.static() 快速托管静态资源
2. 能够使用 express 路由精简项目结构
3. 能够使用常见的 express 中间件
4. 能够使用 express 创建 API 接口
5. 能够在 express 中启用 cors 跨域资源共享

# 2.**初识** **Express**

## 2.1Express 简介

### 2.2.1**什么是** **Express**

官方给出的概念：Express 是基于 Node.js 平台，快速、开放、极简的 Web 开发框架。

通俗的理解：Express 的作用和 Node.js 内置的 http 模块类似，是专门用来创建 Web 服务器的。

**Express** **的本质**：就是一个 npm 上的第三方包，提供了快速创建 Web 服务器的便捷方法。

Express 的中文官网：[ http://www.expressjs.com.cn/](http://www.expressjs.com.cn/)

### 2.2.2**进一步理解** **Express**

思考：不使用 Express 能否创建 Web 服务器？

答案：能，使用 Node.js 提供的原生 http 模块即可。

思考：既生瑜何生亮（有了 http 内置模块，为什么还有用 Express）？

答案：http 内置模块用起来很复杂，开发效率低；Express 是基于内置的 http 模块进一步封装出来的，能够极大的提高开发效率。

思考：http 内置模块与 Express 是什么关系？

答案：类似于浏览器中 Web API 和 jQuery 的关系。后者是基于前者进一步封装出来的。

### 2.2.3**Express** **能做什么**

对于前端程序员来说，最常见的两种服务器，分别是：

-  Web 网站服务器：专门对外提供 Web 网页资源的服务器。
- API 接口服务器：专门对外提供 API 接口的服务器。
- 使用 Express，我们可以方便、快速的创建 Web 网站的服务器或 API 接口的服务器。

## 2.2Express 的基本使用

### 2.1**安装**

在项目所处的目录中，运行如下的终端命令，即可将 express 安装到项目中使用：

```js
npm install express@4.17.11
```

### 2.2**创建基本的** **Web** **服务器**

```js
// 1. 导入 express
const express = require('express')
// 2. 创建 web 服务器
const app = express()

// 3. 启动 web 服务器 app.listen('端口号'，成功后的回调函数)
app.listen(80, () => {
  console.log('express server running at http://127.0.0.1')
})
```

### 2.3**监听** **GET** **请求**

通过 app.get() 方法，可以监听客户端的 GET 请求，具体的语法格式如下：

```js
//参数1:客户端请求的URL地址
//参数2:请求对应的处理函数
//req:请求对象(包含了与请求相关的属性与方法)
//res:响应对象(包含了与响应相关的属性与方法)
app . get( '请求URL' ，function(req, res) { /*处理函数*/ })

```

### 2.4**监听** **POST** **请求**

通过 app.post() 方法，可以监听客户端的 POST 请求，具体的语法格式如下：

```js
//参数1:客户端请求的URL地址
//参数2:请求对应的处理函数
//req:请求对象(包含了与请求相关的属性与方法)
//res:响应对象(包含了与响应相关的属性与方法)
app . post( '请求URL' ，function(req, res) { /*处理函数*/ })
```

### 2.5**把内容响应给客户端**

通过 res.send() 方法，可以把处理好的内容，发送给客户端：

```js
// 1. 导入 express
const express = require('express')
// 2. 创建 web 服务器
const app = express()

// 4. 监听客户端的 GET 和 POST 请求，并向客户端响应具体的内容
app.get('/user', (req, res) => {
  // 调用 express 提供的 res.send() 方法，向客户端响应一个 JSON 对象
  res.send({ name: 'zs', age: 20, gender: '男' })
})

// 3. 启动 web 服务器
app.listen(80, () => {
  console.log('express server running at http://127.0.0.1')
})
```

### 2.6**获取** **URL** **中携带的查询参数**

通过 req.query 对象，可以访问到客户端通过查询字符串的形式，发送到服务器的参数：

```js
app.get('/', (req, res) => {
// req.query 默认是一 个空对象
//客户端使用?name=zs&age=20 这种查询字符串形式，发送到服务器的参数，
//可以通过req. query对象访问到，例如:
// req .query.name req, query age
console. log req. query)
})
```

### 2.7**获取** **URL** **中的动态参数**

通过 req.params 对象，可以访问到 URL 中，通过 **:** 匹配到的动态参数：

```js
// URL地址中，可以通过:参数名的形式，匹配动态参数值
app. get(' /user/:id', (req, res) => {
// req.params 默认是一 个空对象
//里面存放着通过:动态匹配到的参数值
	console. log(req . params)
 })

```

### 2.8托管静态资源

#### 2.8.1**express.static()**

​	express 提供了一个非常好用的函数，叫做 express.static()，通过它，我们可以非常方便地创建一个静态资源服务器，例如，通过如下代码就可以将 public 目录下的图片、CSS 文件、JavaScript 文件对外开放访问了：

```js
app.use(express.static('public'))
```

现在，你就可以访问 public 目录中的所有文件了：

http://localhost:3000/images/bg.jpg

http://localhost:3000/css/style.css

http://localhost:3000/js/login.js

**注意：**Express 在指定的静态目录中查找文件，并对外提供资源的访问路径。因此，存放静态文件的目录名不会出现在 URL 中。

#### 2.8.2**托管多个静态资源目录**

如果要托管多个静态资源目录，请多次调用 express.static() 函数：

```js
app.use(express.static('public'))
app.use(express.static('files'))
```

访问静态资源文件时，express.static() 函数会根据目录的添加顺序查找所需的文件。

#### 2.8.3**挂载路径前缀**

如果希望在托管的静态资源访问路径之前，挂载路径前缀，则可以使用如下的方式：

```js
app.use('/files', express.static('./files'))
```

现在，你就可以通过带有 /public 前缀地址来访问 public 目录中的文件了：

http://localhost:3000/public/images/kitten.jpg

http://localhost:3000/public/css/style.css

http://localhost:3000/public/js/app.js

### 2.9nodemon

#### 2.9.1**为什么要使用** **nodemon**

​	在编写调试 Node.js 项目的时候，如果修改了项目的代码，则需要频繁的手动 close 掉，然后再重新启动，非常繁琐。

​	现在，我们可以使用 nodemon（https://www.npmjs.com/package/nodemon） 这个工具，它能够监听项目文件的变动，当代码被修改后，nodemon 会自动帮我们重启项目，极大方便了开发和调试。

#### 2.9.2**安装** **nodemon**

在终端中，运行如下命令，即可将 nodemon 安装为全局可用的工具：

```js
npm install -g nodemon
```

#### 2.9.3**使用** **nodemon**

​	当基于 Node.js 编写了一个网站应用的时候，传统的方式，是运行 node app.js 命令，来启动项目。这样做的坏处是：代码被修改之后，需要手动重启项目。

现在，我们可以将 node 命令替换为 nodemon 命令，使用 nodemon app.js 来启动项目。这样做的好处是：代码被修改之后，会被 nodemon 监听到，从而实现自动重启项目的效果。

```js
node app.js
//将上面终端命令，替换为下面终端命令，即可实现自动重启
nodemon app.js
```

## 3.Express 路由

### 2.1 路由的概念

#### 2.1.1**什么是路由**

广义上来讲，路由就是映射关系。

#### 2.1.2**现实生活中的路由**

![](\images\02express\2022-03-12_210502.png)

按键 1 -> 业务查询

按键 2 -> 手机充值

按键 3 -> 业务办理

按键 4 -> 密码服务与停复机

按键 5 -> 家庭宽带

按键 6 -> 话费流量

按键 8 -> 集团业务

按键 0 -> 人工服务

在这里，路由是按键与服务之间的映射关系

#### 2.1.3**Express** **中的路由**

在 Express 中，路由指的是客户端的请求与服务器处理函数之间的映射关系。

Express 中的路由分 3 部分组成，分别是请求的类型、请求的 URL 地址、处理函数，格式如下：

```js
app.METHOD(PATH,HANDLER)
```

#### 2.1.4**Express** **中的路由的例子**

```js
// 挂载路由,匹配GET请求URL为/
app.get('/', (req, res) => {
  res.send('hello world.')
})
//匹配POST请求URL为/
app.post('/', (req, res) => {
  res.send('Post Request.')
})
```

**路由的匹配过程**

每当一个请求到达服务器之后，需要先经过路由的匹配，只有匹配成功之后，才会调用对应的处理函数。

在匹配时，会按照路由的顺序进行匹配，如果请求类型和请求的 URL 同时匹配成功，则 Express 会将这次请求，转交给对应的 function 函数进行处理。

![](\images\02express\2022-03-12_211139.png)

路由匹配的注意点：

1. 按照定义的先后顺序进行匹配
2. 请求类型和请求的URL同时匹配成功，才会调用对应的处理函数

### 2.2路由的使用

#### 2.2.1**最简单的用法**

在 Express 中使用路由最简单的方式，就是把路由挂载到 app 上，示例代码如下：

```js
const express = require('express')
//创建Web服务器，命名为App
const app = express()

// 挂载路由
app.get('/', (req, res) => {
  res.send('hello world.')
})
app.post('/', (req, res) => {
  res.send('Post Request.')
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})
```

#### 2.2.2**模块化路由**

为了方便对路由进行模块化的管理，Express **不建议**将路由直接挂载到 app 上，而是推荐将路由抽离为单独的模块。

将路由抽离为单独模块的步骤如下：

1. 创建路由模块对应的 .js 文件
2. 调用 express.Router() 函数创建路由对象
3. 向路由对象上挂载具体的路由
4. 使用 module.exports 向外共享路由对象
5. 使用 app.use() 函数注册路由模块

```js
// 这是路由模块
// 1. 导入 express
const express = require('express')
// 2. 创建路由对象
const router = express.Router()

// 3. 挂载具体的路由
router.get('/user/list', (req, res) => {
  res.send('Get user list.')
})
router.post('/user/add', (req, res) => {
  res.send('Add new user.')
})

// 4. 向外导出路由对象
module.exports = router

```

#### 2.2.3**注册路由模块**

```js
//1.导入路由模块
const express = require('express')
//2.使用app.use()注册路由模块
const app = express()
```

#### 2.2.4**为路由模块添加前缀**

类似于托管静态资源时，为静态资源统一挂载访问前缀一样，路由模块添加前缀的方式也非常简单：

```js
// 1. 导入路由模块
const router = require('./03.router')
// 2. 注册路由模块，并添加统一的访问前缀 /api
app.use('/api', router)
```

# 4.Express 中间件

## 4.1中间件的概念

### 4.1.1**什么是中间件**

中间件（Middleware ），特指业务流程的中间处理环节。

#### 4.1.2**现实生活中的例子**

在处理污水的时候，一般都要经过三个处理环节，从而保证处理过后的废水，达到排放标准。

![](\images\02express\2022-03-12_212947.png)

处理污水的这三个中间处理环节，就可以叫做中间件。

### 4.1.3**Express** **中间件的**调用流程

当一个请求到达 Express 的服务器之后，可以连续调用多个中间件，从而对这次请求进行预处理。

![](\images\02express\2022-03-12_213044.png)

### 4.1.4**Express** **中间件的格式**

Express 的中间件，本质上就是一个 **function** **处理函数**，Express 中间件的格式如下：

![](\images\02express\2022-03-12_213139.png)

注意：中间件函数的形参列表中，必须包含 next 参数。而路由处理函数中只包含 req 和 res。

### 4.1.5**next** **函数的作用**

**next** **函数**是实现多个中间件连续调用的关键，它表示把流转关系转交给下一个中间件或路由。

![](\images\02express\2022-03-12_213227.png)

### 4.1.6**定义中间件函数**

可以通过如下的方式，定义一个最简单的中间件函数：

```js
//常量mw所指向的，就是一一个中间件函数
const mw = function (req, res, next) {
console . log( '这是一个最简单的中间件函数' )
//注意:在当前中间件的业务处理完毕后，必须调用next()函数
//表示把流转关系转交给下一个中间件或路由
	next()
}

```

### 4.1.7**全局生效的中间件**

客户端发起的任何请求，到达服务器之后，都会触发的中间件，叫做全局生效的中间件。

通过调用 app.use(中间件函数)，即可定义一个全局生效的中间件，示例代码如下：

```js
const express = require('express')
const app = express()

//  定义一个最简单的中间件函数
const mw = function (req, res, next) {
 console.log('这是最简单的中间件函数')
   // 把流转关系，转交给下一个中间件或路由
//   next()
 }
//  将 mw 注册为全局生效的中间件
 app.use(mw)
```

### 4.1.8**定义**全局中间件的简化形式

```js

// 这是定义全局中间件的简化形式
app.use((req, res, next) => {
  console.log('这是最简单的中间件函数')
  next()
})
```

### 4.1.9**中间件的**作用

​	多个中间件之间，**共享同一份** **req** **和** **res**。基于这样的特性，我们可以在上游的中间件中，**统一**为 req 或 res 对象添加自定义的属性或方法，供下游的中间件或路由进行使用。

![](\images\02express\2022-03-12_213919.png)

### 1.1.10**定义多个全局中间件**

可以使用 app.use() 连续定义多个全局中间件。客户端请求到达服务器之后，会按照中间件定义的先后顺序依次进行调用，示例代码如下：

```js
const express = require('express')
const app = express()

// 定义第一个全局中间件
app.use((req, res, next) => {
  console.log('调用了第1个全局中间件')
  next()
})
// 定义第二个全局中间件
app.use((req, res, next) => {
  console.log('调用了第2个全局中间件')
  next()
})

// 定义一个路由
app.get('/user', (req, res) => {
  res.send('User page.')
})

app.listen(80, () => {
  console.log('http://127.0.0.1')
})
```

### 1.1.11**局部生效的中间件**

**不使用** app.use() 定义的中间件，叫做局部生效的中间件，示例代码如下：

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 定义中间件函数
const mw1 = (req, res, next) => {
  console.log('调用了局部生效的中间件')
  next()
}

// 2. 创建路由
app.get('/', mw1, (req, res) => {
  res.send('Home page.')
})
app.get('/user', (req, res) => {
  res.send('User page.')
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})
```

### 1.1.12**定义****多个****局部中间件**

可以在路由中，通过如下两种等价的方式，使用多个局部中间件：

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()
// 1. 定义中间件函数
const mw1 = (req, res, next) => {
  console.log('调用了第一个局部生效的中间件')
  next()
}
const mw2 = (req, res, next) => {
  console.log('调用了第二个局部生效的中间件')
  next()
}
// 2. 创建路由
app.get('/', [mw1, mw2], (req, res) => {
  res.send('Home page.')
})
app.get('/user', (req, res) => {
  res.send('User page.')
})
// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})
```

### 1.1.13**了解中间件的5个使用注意事项**

1. 一定要在路由之前注册中间件
2. 客户端发送过来的请求，可以连续调用多个中间件进行处理
3. 执行完中间件的业务代码之后，不要忘记调用 next() 函数
4. 为了防止代码逻辑混乱，调用 next() 函数后不要再写额外的代码
5. 连续调用多个中间件时，多个中间件之间，共享 req 和 res 对象

### 1.1.14中间件的分类

为了方便大家理解和记忆中间件的使用，Express 官方把常见的中间件用法，分成了 5 大类，分别是：

1.  应用级别的中间件
2. 路由级别的中间件错误级别的中间件
3. Express 内置的中间件
4.  第三方的中间件

### 1.1.15**应用级别的中间件**

通过 app.use() 或 app.get() 或 app.post() ，绑定到 app 实例上的中间件，叫做应用级别的中间件，代码示例如下：

```js
 //应用级别的中间件(全局中间件)
 app.use(req, res, next) => {
	next( )
 })
 //1应用级别的中间件(局部中间件)
 app.get('/'. mw1, (req, res) => {
	res . send 'Home page.' )
}
```

### 1.1.16**路由级别的中间件**

​	绑定到 express.Router() 实例上的中间件，叫做路由级别的中间件。它的用法和应用级别中间件没有任何区别。只不过，应用级别中间件是绑定到 app 实例上，路由级别中间件绑定到 router 实例上，代码示例如下：

```js
 var app = express()
 var router express .Router()
 //路由吸别的中间件
router.use(function (req, res, next) {
    console.log('Time:', Date . now())
    next()
}
 app.use('/'. router 
```

### 1.1.17**错误级别的中间件**

错误级别中间件的**作用**：专门用来捕获整个项目中发生的异常错误，从而防止项目异常崩溃的问题。

**格式**：错误级别中间件的 function 处理函数中，必须有 4 个形参，形参顺序从前到后，分别是 (err, req, res, next)。

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 定义路由
app.get('/', (req, res) => {
  // 1.1 人为的制造错误
  throw new Error('服务器内部发生了错误！')
  res.send('Home page.')
})
// 2. 定义错误级别的中间件，捕获整个项目的异常错误，从而防止程序的崩溃
app.use((err, req, res, next) => {
  console.log('发生了错误！' + err.message)
  res.send('Error：' + err.message)
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})
```

**注意：**错误级别的中间件，必须注册在所有路由之后！

### 1.1.18**Express内置的中间件**

自 Express 4.16.0 版本开始，Express 内置了 3 个常用的中间件，极大的提高了 Express 项目的开发效率和体验：

1.  express.static 快速托管静态资源的内置中间件，例如： HTML 文件、图片、CSS 样式等（无兼容性）
2.  express.json 解析 JSON 格式的请求体数据（有兼容性，仅在 4.16.0+ 版本中可用）
3.  express.urlencoded 解析 URL-encoded 格式的请求体数据（有兼容性，仅在 4.16.0+ 版本中可用）

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 注意：除了错误级别的中间件，其他的中间件，必须在路由之前进行配置
// 通过 express.json() 这个中间件，解析表单中的 JSON 格式的数据
app.use(express.json())
// 通过 express.urlencoded() 这个中间件，来解析 表单中的 url-encoded 格式的数据
app.use(express.urlencoded({ extended: false }))

app.post('/user', (req, res) => {
  // 在服务器，可以使用 req.body 这个属性，来接收客户端发送过来的请求体数据
  // 默认情况下，如果不配置解析表单数据的中间件，则 req.body 默认等于 undefined
  console.log(req.body)
  res.send('ok')
})

app.post('/book', (req, res) => {
  // 在服务器端，可以通过 req,body 来获取 JSON 格式的表单数据和 url-encoded 格式的数据
  console.log(req.body)
  res.send('ok')
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})
```

### 1.1.19**第三方的中间件**

非 Express 官方内置的，而是由第三方开发出来的中间件，叫做第三方中间件。在项目中，大家可以按需下载并配置第三方中间件，从而提高项目的开发效率。

例如：在 express@4.16.0 之前的版本中，经常使用 body-parser 这个第三方中间件，来解析请求体数据。使用步骤如下：

1. 运行 npm install body-parser 安装中间件
2. 使用 require 导入中间件
3. 调用 app.use() 注册并使用中间件

**注意：**Express 内置的 express.urlencoded 中间件，就是基于 body-parser 这个第三方中间件进一步封装出来的。

### 1.1.20**需求描述与实现步骤**

自己手动模拟一个类似于 express.urlencoded 这样的中间件，来解析 POST 提交到服务器的表单数据。

实现步骤：

1. 定义中间件
2. 监听 req 的 data 事件
3. 监听 req 的 end 事件
4. 使用 querystring 模块解析请求体数据
5. 将解析出来的数据对象挂载为 req.body
6. 将自定义中间件封装为模块

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()
// 导入 Node.js 内置的 querystring 模块
const qs = require('querystring')

// 这是解析表单数据的中间件
app.use((req, res, next) => {
  // 定义中间件具体的业务逻辑
  // 1. 定义一个 str 字符串，专门用来存储客户端发送过来的请求体数据
  let str = ''
  // 2. 监听 req 的 data 事件
  req.on('data', (chunk) => {
    str += chunk
  })
  // 3. 监听 req 的 end 事件
  req.on('end', () => {
    // 在 str 中存放的是完整的请求体数据
    // console.log(str)
    // TODO: 把字符串格式的请求体数据，解析成对象格式
    const body = qs.parse(str)
    req.body = body
    next()
  })
})

app.post('/user', (req, res) => {
  res.send(req.body)
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})
```

- **将自定义中间件封装为模块**

```js
// 导入 express 模块
const express = require('express')
// 创建 express 的服务器实例
const app = express()

// 1. 导入自己封装的中间件模块
const customBodyParser = require('./14.custom-body-parser')
// 2. 将自定义的中间件函数，注册为全局可用的中间件
app.use(customBodyParser)

app.post('/user', (req, res) => {
  res.send(req.body)
})

// 调用 app.listen 方法，指定端口号并启动web服务器
app.listen(80, function () {
  console.log('Express server running at http://127.0.0.1')
})

```

# 2.**使用** **Express** **写接口**

## 2.1**创建基本的服务器**

```js
// 导入 express
const express = require('express')
// 创建服务器实例
const app = express()

// 启动服务器
app.listen(80, () => {
  console.log('express server running at http://127.0.0.1')
})
```

## 2.2**创建** **API** **路由模块**

```js
//apiRouter.js路由模块
const express = require('express')
const router = express.Router()
module.exports = router

/*********************************/
//app.js导入并注册模块

// 导入路由模块
const router = require('./16.apiRouter')
// 把路由模块，注册到 app 上
app.use('/api', router)
```

### 2.3**编写** **GET** **接口**

```js
//apiRouter.js
// 在这里挂载对应的路由
router.get('/get', (req, res) => {
  // 通过 req.query 获取客户端通过查询字符串，发送到服务器的数据
  const query = req.query
  // 调用 res.send() 方法，向客户端响应处理的结果
  res.send({
    status: 0, // 0 表示处理成功，1 表示处理失败
    msg: 'GET 请求成功！', // 状态的描述
    data: query, // 需要响应给客户端的数据
  })
})
```

## 2.4**编写** **POST** **接口**

```js
//apiRouter.js
// 定义 POST 接口
router.post('/post', (req, res) => {
  // 通过 req.body 获取请求体中包含的 url-encoded 格式的数据
  const body = req.body
  // 调用 res.send() 方法，向客户端响应结果
  res.send({
    status: 0,
    msg: 'POST 请求成功！',
    data: body,
  })
})

// 定义 DELETE 接口
router.delete('/delete', (req, res) => {
  res.send({
    status: 0,
    msg: 'DELETE请求成功',
  })
})
```

**注意：**如果要获取 URL-encoded 格式的请求体数据，必须配置中间件 app.use(express.urlencoded({ extended: false }))

CORS 跨域资源共享

# 3、**接口的**跨域问题

刚才编写的 GET 和 POST接口，存在一个很严重的问题：不支持跨域请求。

解决接口跨域问题的方案主要有两种：

1. CORS（主流的解决方案，推荐使用）
2.  JSONP（有缺陷的解决方案：只支持 GET 请求）

## 3.1CORS 跨域资源共享

### 3.1.1**使用** **cors** **中间件解决跨域问题**

cors 是 Express 的一个第三方中间件。通过安装和配置 cors 中间件，可以很方便地解决跨域问题。

使用步骤分为如下 3 步：

1. 运行 npm install cors 安装中间件
2. 使用 const cors = require('cors') 导入中间件
3. 在路由之前调用 app.use(cors()) 配置中间件

### 2.1.2**什么是** **CORS**

​	CORS （Cross-Origin Resource Sharing，跨域资源共享）由一系列 HTTP 响应头组成，**这些** **HTTP** **响应头决定浏览器是否阻止前端** **JS** **代码跨域获取资源**。

浏览器的同源安全策略默认会阻止网页“跨域”获取资源。但如果接口服务器配置了 CORS 相关的 HTTP 响应头，就可以解除浏览器端的跨域访问限制。

![](\images\02express\2022-03-12_221412.png)

### 2.1.3**CORS** **的注意事项**

1. CORS 主要在服务器端进行配置。客户端浏览器**无须做任何额外的配置**，即可请求开启了 CORS 的接口。
2.  CORS 在浏览器中有兼容性。只有支持 XMLHttpRequest Level2 的浏览器，才能正常访问开启了 CORS 的服务端接口（例如：IE10+、Chrome4+、FireFox3.5+）。

### 2.1.4**CORS** **响应头部** **- Access-Control-Allow-Origin** 

响应头部中可以携带一个 **Access-Control-Allow-Origin** 字段，其语法如下:

其中，origin 参数的值指定了允许访问该资源的外域 URL。

```js
 Access-Control-Allow-0rigin: <origin> |*

```

例如，下面的字段值将**只允许**来自 http://itcast.cn 的请求：

```js
 res.setHeader( Access-Control-Allow-0rigin' ,'http://itcast.cn')
```

### 2.1.5**CORS** **响应头部** **- Access-Control-Allow-**Origin

如果指定了 Access-Control-Allow-Origin 字段的值为通配符 *****，表示允许来自任何域的请求，示例代码如下：

```js
res.setHeader( Access-Control-Allow-0rigin' ,'*' )
```

#### 2.1.6**CORS** **响应头部** **- Access-Control-Allow-Headers**

默认情况下，CORS **仅**支持客户端向服务器发送如下的 9 个请求头：

Accept、Accept-Language、Content-Language、DPR、Downlink、Save-Data、Viewport-Width、Width 、Content-Type （值仅限于 text/plain、multipart/form-data、application/x-www-form-urlencoded 三者之一）

如果客户端向服务器发送了额外的请求头信息，则需要在服务器端，通过 Access-Control-Allow-Headers 对额外的请求头进行声明，否则这次请求会失败！

```js
res.setHeader( 'Access-Control-Allow-Headers' ,'Content-Type,X-Custom-Header')
```

### 2.1.7**CORS** **响应头部** **- Access-Control-Allow-Methods**

默认情况下，CORS 仅支持客户端发起 GET、POST、HEAD 请求。

如果客户端希望通过 PUT、DELETE 等方式请求服务器的资源，则需要在服务器端，通过 Access-Control-Alow-Methods来指明实际请求所允许使用的 HTTP 方法。

示例代码如下：

```js
//只允许GET、POST、HEAD、HEAD请求。
res.setHeader( 'Access-Control-Allow-Methods' ,'POST,GET,DELET,HEAD')
//允许所有请求
res.setHeader( 'Access-Control-Allow-Methods' ,'*')
```

### 2.1.8**CORS请求的分类**

客户端在请求 CORS 接口时，根据请求方式和请求头的不同，可以将 CORS 的请求分为两大类，分别是：

1. 简单请求
2. 预检请求

- **简单请求**

同时满足以下两大条件的请求，就属于简单请求：

1. 请求方式：GET、POST、HEAD 三者之一
2. HTTP 头部信息不超过以下几种字段：无自定义头部字段、Accept、Accept-Language、Content-Language、DPR、Downlink、Save-Data、Viewport-Width、Width 、Content-Type（只有三个值application/x-www-form-urlencoded、multipart/form-data、text/plain）

- **预检请求**

只要符合以下任何一个条件的请求，都需要进行预检请求：

1.  请求方式为 GET、POST、HEAD 之外的请求 Method 类型
2. 请求头中包含自定义头部字段
3. 向服务器发送了 application/json 格式的数据

在浏览器与服务器正式通信之前，浏览器会先发送 OPTION 请求进行预检，以获知服务器是否允许该实际请求，所以这一次的 OPTION 请求称为“预检请求”。服务器成功响应预检请求后，才会发送真正的请求，并且携带真实数据。

- **简单请求和预检请求的区别**

  **简单请求的特点**：客户端与服务器之间只会发生一次请求。

  **预检请求的特点**：客户端与服务器之间会发生两次请求，OPTION 预检请求成功之后，才会发起真正的请求。

## 3.2**JSONP** **接口**

### 3.2.1**回顾** **JSONP** **的概念与特点**

概念：浏览器端通过 <script> 标签的 src 属性，请求服务器上的数据，同时，服务器返回一个函数的调用。这种请求数据的方式叫做 JSONP。

特点：

1. JSONP 不属于真正的 Ajax 请求，因为它没有使用 XMLHttpRequest 这个对象。
2. JSONP 仅支持 GET 请求，不支持 POST、PUT、DELETE 等请求。

#### 3.2.2**创建** **JSONP** **接口的注意事项**

​	如果项目中已经配置了 CORS 跨域资源共享，为了**防止冲突**，必须在配置 CORS 中间件之前声明 JSONP 的接口。否则 JSONP 接口会被处理成开启了 CORS 的接口。示例代码如下：

```js
 //优先创建JSONP 接口[这个接口不会被处理成CORS接口]
app. get( ' /api/jsonp', (req, res) => { }
//再配置CORS中间件[后续的所有接口，都会被处理成CORS接口]
 app. use( cors()
//1这是一个开启了CORS 的接口
app. get(/api/get', (req, res) => { }) 
```

### 3.2.3**实现** **JSONP** **接口的步骤**

1. 获取客户端发送过来的回调函数的名字
2. 得到要通过 JSONP 形式发送给客户端的数据
3. 根据前两步得到的数据，拼接出一个函数调用的字符串
4. 把上一步拼接得到的字符串，响应给客户端的 <script> 标签进行解析执行

### 3.2.4**实现** **JSONP** **接口的具体代码**

```js
app . get('/api/jsonp', (req, res) => {
    //1.获取客户端发送过来的回调函数的名字
    const funcName = req . query . callback
    // 2.得到要通过JSONP形式发送给客户端的数据
    const data = { 
        name:'ZS'
        age: 22 
    }
    // 3.根据前两步得到的数据，拼接出一个函数调用的字符串
    const scriptStr = ${funcName}($ {JSON str ingify(data)})
    // 4.把上一步拼接得到的字符串，响应给客户端的<script> 标签进行解析执行
    res . send( scriptStr)
})
```

### 2.2.5**在网页中使用** **jQuery** **发起** **JSONP** **请求**

调用 $.ajax() 函数，提供 JSONP 的配置选项，从而发起 JSONP 请求，示例代码如下：

```js
 // 4. 为 JSONP 按钮绑定点击事件处理函数
        $('#btnJSONP').on('click', function () {
          $.ajax({
            type: 'GET',
            url: 'http://127.0.0.1/api/jsonp',
            dataType: 'jsonp',
            success: function (res) {
              console.log(res)
            },
          })
        })
```

# 七、**数据库与身份认证**（MySQL）

# 1、目标

1. 能够知道如何配置 MySQL 数据库环境
2. 能够认识并使用常见的 SQL 语句操作数据库
3. 能够在项目中操作 MySQL 数据库
4. 能够了解 Session 的实现原理
5. 能够了解 JWT 的实现原理

# 2、**数据库的基本概念**

## 2.1 什么是数据库

​	数据库（database）是用来组织、存储和管理数据的仓库。

​	当今世界是一个充满着数据的互联网世界，充斥着大量的数据。数据的来源有很多，比如出行记录、消费记录、浏览的网页、发送的消息等等。除了文本类型的数据，图像、音乐、声音都是数据。

​	为了方便管理互联网世界中的数据，就有了数据库管理系统的概念（简称：数据库）。用户可以对数据库中的数据进行新增、查询、更新、删除等操作。

## 2.2常见的数据库及分类

市面上的数据库有很多种，最常见的数据库有如下几个：

- MySQL 数据库（目前使用最广泛、流行度最高的开源免费数据库；Community + Enterprise）

- Oracle 数据库（收费）

- SQL Server 数据库（收费）

-  Mongodb 数据库（Community + Enterprise）

  其中，MySQL、Oracle、SQL Server 属于**传统型数据库**（又叫做：关系型数据库 或 SQL 数据库），这三者的设计理念相同，用法比较类似。

而 Mongodb 属于**新型数据库**（又叫做：非关系型数据库 或 NoSQL 数据库），它在一定程度上弥补了传统型数据库的缺陷。

## 2.3传统型数据库的数据组织结构

数据的组织结构：指的就是数据以什么样的结构进行存储。

<img src="\images\03MySQL\2022-03-12_223811.png" style="zoom:75%;" />

传统型数据库的数据组织结构，与 Excel 中数据的组织结构比较类似。因此，我们可以对比着 Excel 来了解和学习传统型数据库的数据组织结构。

传统型数据库的数据组织结构

## 2.4**Excel** **的数据组织结构**

每个 Excel 中，数据的组织结构分别为工作簿、工作表、数据行、列这 4 大部分组成。

<img src="L:\学习笔记\study-notes\nodeJS\images\03MySQL\2022-03-12_223957.png" style="zoom:75%;" />

1. 整个 Excel 叫做工作簿
2. users 和 books 是工作表
3. users 工作表中有 3 行数据
4. 每行数据由 6 列信息组成
5. 每列信息都有对应的数据类型

## 2.5**传统型数据库的数据组织结构**

在传统型数据库中，数据的组织结构分为数据库(database)、数据表(table)、数据行(row)、字段(field)这 4 大部分组成

1.  数据库类似于 Excel 的工作簿
2.  数据表类似于 Excel 的工作表
3.  数据行类似于 Excel 的每一行数据
4.  字段类似于 Excel 的列
5.  每个字段都有对应的数据类型

## 2.6**实际开发中库、表、行、字段的关系**

1. 在实际项目开发中，一般情况下，每个项目都对应独立的数据库。
2. 不同的数据，要存储到数据库的不同表中，例如：用户数据存储到 users 表中，图书数据存储到 books 表中。
3. 每个表中具体存储哪些信息，由字段来决定，例如：我们可以为 users 表设计 id、username、password 这 3 个字段。
4. 表中的行，代表每一条具体的数据。

# 3、**安装并配置** **MySQL**

## 3.1了解需要安装哪些MySQL相关的软件

对于开发人员来说，只需要安装 MySQL Server 和 MySQL Workbench 这两个软件，就能满足开发的需要了。

lMySQL Server：专门用来提供数据存储和服务的软件。

MySQL Workbench：可视化的 MySQL 管理工具，通过它，可以方便的操作存储在 MySQL Server 中的数据。

## 3.2MySQL 在 Mac 环境下的安装

在 Mac 环境下安装 MySQL 的过程比 Windows 环境下的步骤简单很多：

①先运行 **mysql-8.0.19-macos10.15-x86_64.dmg** 这个安装包，将 MySQL Server 安装到 Mac 系统

②再运行 **mysql-workbench-community-8.0.19-macos-x86_64.dmg** 这个安装包，将可视化的 MySQL Workbench 工具安装到 Mac 系统

具体的安装教程，可以参考 资料 -> MySQL for Mac ->安装教程 - Mac系统安装MySql -> README.md

## 3.3MySQL 在 Windows 环境下的安装

​	在 Windows 环境下安装 MySQL，只需要运行 **mysql-installer-community-8.0.19.0.msi** 这个安装包，就能一次性将 MySQL Server 和 MySQL Workbench 安装到自己的电脑上。

具体的安装教程，可以参考 资料 -> MySQL for Windows ->安装教程 - Windows系统安装MySql -> README.md 

# 4、MySQL 的基本使用

## 4.1使用 MySQL Workbench 管理数据库

### 4.1.1**连接数据库**

![](\images\03MySQL\2022-03-12_224701.png)

### 4.1.2**了解主界面的组成部分**

![](\images\03MySQL\2022-03-12_224819.png)

### 4.1.3**创建数据库**

![](\images\03MySQL\2022-03-12_224944.png)

### 4.1.4**创建数据表**

![](\images\03MySQL\2022-03-12_225036.png)

DataType 数据类型：

① int 整数

② varchar(len) 字符串

③ tinyint(1) 布尔值

字段的特殊标识：

① PK（Primary Key）主键、唯一标识

② NN（Not Null）值不允许为空

③ UQ（Unique）值唯一

 AI（Auto Increment）值自动增长

### 4.1.5**向表中写入数据**

![](\images\03MySQL\2022-03-12_225124.png)

# 5、使用 SQL 管理数据库

## 5.1**什么是** **SQL**

SQL（英文全称：Structured Query Language）是结构化查询语言，专门用来访问和处理数据库的编程语言。能够让我们**以编程的形式**，**操作数据库里面的数据**。

三个关键点：

1. SQL 是一门数据库编程语言
2. 使用 SQL 语言编写出来的代码，叫做 SQL 语句
3. SQL 语言只能在关系型数据库中使用（例如 MySQL、Oracle、SQL Server）。非关系型数据库（例如 Mongodb）不支持 SQL 语言

## 5.2**SQL** **能做什么**

1. 从数据库中查询数据
2.  向数据库中插入新的数据
3.  更新数据库中的数据
4.  从数据库删除数据
5. 可以创建新数据库
6. 可在数据库中创建新表
7.  可在数据库中创建存储过程、视图
8.  etc…

## 5.3**SQL** 的学习目标

重点掌握如何使用 SQL 从数据表中：

查询数据（select） 、插入数据（insert into） 、更新数据（update） 、删除数据（delete）

额外需要掌握的 4 种 SQL 语法：

where 条件、and 和 or 运算符、order by 排序、count(*) 函数

### 5.3.1SQL 的 SELECT 语句

**语法**：SELECT 语句用于从**表中查询数据**。执行的结果被存储在一个结果表中（称为结果集）。语法格式如下：

```sql
--这是注释
--从FROM 指定的[表中]，查询出[所有的]数据。 ★表示[所有列]
SELECT * FROM表名称

--从FROM指定的[表中] ,查询出指定列名称(字段) 的数据。
SELECT 列名称 FROM表名称
```

注意：SQL 语句中的关键字对**大小写不敏感**。SELECT 等效于 select，FROM 等效于 from。

### 5.3.2**SELECT \*** **示例**

我们希望从 users 表中选取所有的列，可以使用符号 * 取代列的名称，示例如下：

```sql
--通过 * 把 users 表中所有的数据查询出来
select * from users
```

### 5.3.3**SELECT** **列名称** **示例**

如需获取名为 "username" 和 "password" 的列的内容（从名为 "users" 的数据库表），请使用下面的 SELECT 语句：

```sql
--从 users 表中把 username 和 password 对应的数据查询出来
 select username, password from users
```

## 5.4SQL 的 INSERT INTO 语句

**语法**：INSERT INTO 语句用于向数据表中插入新的数据行，语法格式如下：

```
 --语法解读:向指定的表中，插入如下几列数据，列的值通过values————指定
 --注意:列和值要一一对应， 多个列和多个值之间，使用英文的逗号分隔
INSERT INTO table name (列1,列2....) VALUES (值1,值.....)
```

### 5.4.1**INSERT INTO** **示例**

向 users 表中，插入一条 username 为 tony stark，password 为 098123 的用户数据，示例如下：

```sql
--向 users 表中，插入新数据，username 的值为 tony stark  password 的值为 098123
insert into users (username, password) values ('tony stark', '098123')
```

## 5.5**SQL** **的** **UPDATE** **语句**

**语法**：Update 语句用于修改表中的数据。语法格式如下：

```sql
 --语法解读:
--1.用UPDATE指定要更新哪个表中的数据
--2.用SET指定列对应的新值
--3.用WHERE指定更新的条件
UPDATE 表名称SET列名称=新值WHERE列名称=某值
```

### 5.5.1**UPDATE** **示例** **-** **更新某一行中的一个列**

把 users 表中 id 为 7 的用户密码，更新为 888888。示例如下：

```sql
--将 id 为 4 的用户密码，更新成 888888
update users set password='888888' where id=4
```

## 5.6SQL 的 UPDATE 语句

#### **5.5.1UPDATE** **示例** **-** **更新某一行中的若干列**

把 users 表中 id 为 2 的用户密码和用户状态，分别更新为 admin123 和 1。示例如下：

```sql
--更新 id 为 2 的用户，把用户密码更新为 admin123  同时，把用户的状态更新为 1
update users set password='admin123', status=1 where id=2
```

## 5.7SQL 的 DELETE 语句

**语法**：DELETE 语句用于删除表中的行。语法格式如下：

```sql
--语法解读: 
--从指定的表中，根据WHERE 条件，删除对应的数据行
DELETE FROM 表名称 WHERE 列名称=值
```

### 5.7.1**DELETE** **示例**

从 users 表中，删除 id 为 4 的用户，示例如下：

```sql
--删除 users 表中， id 为 4 的用户
delete from users where id=4
```

## 5.8SQL 的 WHERE 子句

**语法**：WHERE 子句用于限定选择的标准。在 SELECT、UPDATE、DELETE 语句中，皆可使用 WHERE 子句来限定选择的标准。

```sql
--查询语句中的WHERE条件
SELECT列名称FROM表名称WHERE列运算符值
--更新语句中的WHERE条件
--UPDATE表名称SET列=新值WHERE列运算符值
--删除语句中的WHERE条件
DELETE FROM表名称WHERE列运算符值
```

## 5.9SQL 的 WHERE 子句

### 5.9.1**可在** **WHERE** **子句中使用的****运算符**

下面的运算符可在 WHERE 子句中使用，用来限定选择的标准：

![](L:\学习笔记\study-notes\nodeJS\images\03MySQL\2022-03-12_231118.png)

注意：在某些版本的 SQL 中，操作符 <> 可以写为 !=

### 5.9.2**WHERE** **子句示例**

可以通过 WHERE 子句来限定 SELECT 的查询条件：

```sql
--演示 where 子句的使用
select * from users where status=1
select * from users where id>=2
select * from users where username<>'ls'
select * from users where username!='ls'
```

## 5.10SQL 的 AND 和 OR 运算符

**语法**

- AND 和 OR 可在 WHERE 子语句中把两个或多个条件结合起来。

- AND 表示必须同时满足多个条件，相当于 JavaScript 中的 && 运算符，例如 if (a !== 10 && a !== 20)

- OR 表示只要满足任意一个条件即可，相当于 JavaScript 中的 || 运算符，例如 if(a !== 10 || a !== 20)

### 5.10.1**AND** **运算符****示例**

使用 AND 来显示所有 status 为 0，并且 id 小于 3 的用户：

```sql
-- 使用 AND 来显示所有状态为0且id小于3的用户
select * from users where status=0 and id<3
```

