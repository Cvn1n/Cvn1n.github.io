+++
title = "关于CentOS:xxx is not in the sudoers file"
template = "page.html"
date = 2024-02-15T07:38:00Z
[taxonomies]
tags = ["CentOS"]
[extra]
summary = " "
mathjax = "tex-mml"
+++

su -
<br>
u+w /etc/sudoers
<br>
vim /etc/sudoers
<br>
按"I"编辑：
<br>
root ALL=(ALL) ALL下方加入
<br>
XXX ALL=(ALL) ALL

ESC,随后:wq 退出

最后撤销文件的写权限chmod u-w /etc/sudoers

不然将引起"sudo: /etc/sudoers is mode 0640, should be 0440" 问题！！！
