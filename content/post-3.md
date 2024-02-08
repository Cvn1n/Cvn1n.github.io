+++
title = "搭建基于 Node.js 的 Web 服务器并统计静态HTML访客数量教程"
template = "page.html"
date = 2024-02-09T05:47:00Z
[taxonomies]
tags = ["教程"]
[extra]
summary = "无需编程基础-工具的使用"
mathjax = "tex-mml"
+++




## 步骤大纲

1. **创建CSS文件** : 首先，我们需要建个CSS文件，空的也可以——我们只需要这个文件的请求来统计访问次数
2. **设置服务器端点** : 搭个Node.js服务器，拿来接收对CSS文件的请求，并在返回文件之前递增一个计数器。等下会用Express框架来创建这个服务器
3. **服务器端代码** : 编写服务器端代码来实现递增计数器的逻辑，并返回CSS文件。
4. **在网页中引用CSS文件** : 在静态网页中引用这个CSS文件，网页加载时会发送对这个文件的请求,触发服务器端的统计逻辑。
5. **运行服务器** : 启动你的Node.js服务器，确保它可以接收来自网页的请求，并递增计数器。
6. **访问统计** : 检查服务器端的日志或控制台输出，以查看访问次数的统计信息。

<a href="https://imgse.com/i/pF3ua5j"><img src="https://s11.ax1x.com/2024/02/09/pF3ua5j.png" alt="pF3ua5j.png" border="0" /></a>

用 Node.js 搭建一个简单的 Web 服务器，并在服务器上加载一个 CSS 文件。
<br>
同时添加代码来统计访客数量并记录每个访问请求。

---

开始：详细步骤教程
-


- # 步骤 1:环境准备
首先，你需要在你的计算机上安装 Node.js。
<br>
你可以从 [Node.js 官方网站](https://nodejs.org/zh-cn/)
<br>
下载并安装 Node.js——
<br>
我们要用到JavaScript
<br>

--------------------------------

<details>
  <summary>问题之——什么是Node.js?</summary>
  <pre><code>
很简单，你这么理解。 
鱼要活在水里，人要生在陆上
没有Java运行不了Minecraft，没有C++无法运行系统
而没有Node.js，无法运行JavaScript
可以说——它是一种"环境"
</code></pre>
</details>

<details>
  <summary>问题之——Node是环境,为什么又说Node.js Web 服务器</summary>
  <pre><code>
这个就更简单了，使用Node.js部署的网页，叫做Node.js Web服务器
</code></pre>
</details>

<details>
  <summary>问题之——什么事JavaScript</summary>
  <pre><code>
奥——你就当它，是一种编程语言，等下要用到它，不过看不懂也没关系
</code></pre>
</details>

↑↑↑如果你想知道，点击查看

-------------------------

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

- # 步骤 2: 创建项目目录

保存文件后，打开CMD，进入到你的项目文件夹中。
<br>
运行命令安装 Express 框架：

```
npm install express
``````

<details>
  <summary>问题之什么是Express?</summary>
  <pre><code>
当它是Node.js的一个扩展插件，总之 我们要用到它，所以安装它就好
  </code></pre>
</details>

<br>

↑↑↑如果你想知道，点击查看

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

假设你的静态博客的 HTML 文件是 `index.html`，那么你需要在该文件中添加如下代码：

```
<link rel="stylesheet" type="text/css" href="http://localhost:3000/styles.css">
```

请确保替换 `http://localhost:3000/styles.css` 为你服务器的IP地址

这样，当浏览器访问你的博客页面时，
<br>
就会自动加载这个 CSS 文件，浏览器会请求加载这个 CSS 文件
<br>
并且在加载时会访问你的 Node.js 服务器，从而触发计数器递增。

//如果你部署在本地的话——可以考虑用端口映射解决公网问题

- #  步骤 5: 查看结果

如果你愿意一个一个数有多少个"Received request for CSS file"  来判断有多少访问
<br>
也是可行的 XD
<br>
不过你可以通过访问 `http://localhost:37626/visit-count` 来获取当前的访问次数。

#  其他

参考链接:[CSDN-静态页面的浏览量_如何获得静态网站的实际浏览量](https://blog.csdn.net/cuk0051/article/details/108343198) (该文章作者使用的是一张PNG图片)

最新更新于 2024.02.09 3：54
