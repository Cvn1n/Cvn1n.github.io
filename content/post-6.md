+++
title = "使用Nginx反向代理实现子域名映射到不同端口的网站"
template = "page.html"
date = 2024-02-17T18:25:00Z
[taxonomies]
tags = ["教程", "域名解析" ]
[extra]
summary = "如何为同一IP下的不同项目分配二级域名？"
mathjax = "tex-mml"
+++

# 使用Nginx反向代理实现子域名映射到不同端口的网站

示例情景

现在我手上拥有一个域名:  test.com
<br>
我还有一台服务器
<br>
拥有IP地址>

127.0.0.1:57784(私有)
<br>
128.0.0.1:57784(公)

上面分别已部署了两个网站
<br>
它们通过128.0.0.1:57784和128.0.0.1:57783访问

需求:
<br>
让128.0.0.1:57783的网站通过t3.test.com访问
<br>
让128.0.0..148:57784的网站通过t4.test.online访问
<br>
应该怎么做

=================================================================================================================================



1. **配置DNS** ：
   * 登录你的域名注册商或DNS托管提供商的控制面板。
   * 添加两个A记录，将 `t3.test.com` 和 `4.test.online` 分别指向你的公网IP地址 `47.96.139.148`。
2. **配置Nginx** ：
   
   * 修改配置文件，例如：

```
server {
    listen 80;
    server_name tc.v1va.online;

    location / {
        proxy_pass http://127.0.0.1:57784;  # 将请求代理到本地端口
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

```
server {
    listen 80;
    server_name file.v1va.online;

    location / {
        proxy_pass http://127.0.0.1:57783;  # 将请求代理到本地端口
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```


* (只是示例,自行对照调整)然后重新加载Nginx配置，以使更改生效：`sudo systemctl reload nginx`。

3. **测试** ：

在浏览器中输入 `t3.test.com`和`t4.test.com`，看看是否能够正确访问到相应的网站。









* 
