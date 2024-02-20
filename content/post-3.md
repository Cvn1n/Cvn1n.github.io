+++
title = "搭建基于 Node.js 的 Web 服务器并统计静态HTML访客数量教程"
template = "page.html"
date = 2024-02-09T05:47:00Z
[taxonomies]
tags = ["教程"]
[extra]
summary = "工具的使用"
mathjax = "tex-mml"
+++




## 步骤大纲

搭个Node.js服务器，包含一个CSS文件，用于接收对CSS文件的请求，并在返回文件前递增一个计数器。等下会用Express框架来创建这个服务器。

让你的静态网页能在加载时发送对这个css文件请求，触发node.js服务器的计算器递增

<a href="https://imgse.com/i/pF3ua5j"><img src="https://s11.ax1x.com/2024/02/09/pF3ua5j.png" alt="pF3ua5j.png" border="0" /></a>

---

开始：详细步骤教程
-


- # 步骤 1:环境准备
首先，你需要在你的计算机上安装 Node.js。
<br>
你可以从 [Node.js 官方网站](https://nodejs.org/zh-cn/)
<br>
下载并安装 Node.js
<br>

接下来，创建个新文件夹，用来存放Node.js Web服务器。
<br>
在文件夹中，创建一个新的 JavaScript 文件，比如 `app.js`。
<br>
打开 `app.js` 文件，将以下代码复制进去：

```
// 引入 Express 框架
const express = require('express');
// 创建 Express 应用
const app = express();

// 初始化计数器，用于记录 CSS 文件的请求次数
let counter = 0;

// 处理 CSS 文件请求的路由
app.get('/styles.css', (req, res) => {
  // 记录请求到达
  console.log('Received request for CSS file');

  // 每次有请求时递增计数器
  counter++;

  // 设置响应头，指定返回的内容类型为 CSS
  res.setHeader('Content-Type', 'text/css');

  // 返回 CSS 内容，这里可以是你的 CSS 样式
  res.send(`
    body {
      background-color: lightblue;
    }
    /* 更多 CSS 样式 */
  `);
});

// 处理获取访问次数的请求
app.get('/visit-count', (req, res) => {
  // 返回当前的访问次数
  res.send(`Total visits: ${counter}`);
});

// 启动服务器，监听指定端口
const PORT = process.env.PORT || 37626;
app.listen(PORT, () => {
  // 在控制台输出服务器启动的消息
  console.log(`Server is running on port ${PORT}`);
});
```

//其中const PORT = process.env.PORT || 37626; 这里可以改成你要监听的端口!!!!!

- # 步骤 2: 安装Express 框架

保存文件后，打开CMD，进入到你的项目文件夹中。
<br>
运行命令安装 Express 框架：

```
npm install express
``````

- # 步骤 3: 运行服务器

完成步骤二后

在.js文件在的路径下打开命令行中使用以下命令运行服务器：

```
node server.js
```

<br>

然后尝试访问根路径（例如 `http://localhost:37626/`）,
<br>
你应该能够看到 "Hello, World!" 这条消息。
<br>
（这说明你的程序正常在运行）

- # 步骤 4: 为你的HTML引用这个 CSS 文件

在你的html文件中添加如下代码：

```
<link rel="stylesheet" type="text/css" href="http://localhost:3000/styles.css">
```

请确保替换 `http://localhost:3000/styles.css` 为你服务器的IP地址

这样，当浏览器访问你页面时，
<br>
浏览器会请求加载这个 CSS 文件
<br>
并且在加载时访问你的 Node.js 服务器，从而触发计数器递增。



- #  步骤 5: 查看结果

可以通过访问 `http://localhost:37626/visit-count` 来获取当前的访问次数。
<br>
或者数数控制台有几条回馈。

--------------

参考链接:[CSDN-静态页面的浏览量_如何获得静态网站的实际浏览量](https://blog.csdn.net/cuk0051/article/details/108343198) 
最新更新于 2024.02.1 14：23
