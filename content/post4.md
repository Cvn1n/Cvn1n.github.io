+++
title = "关于CentOS:xxx is not in the sudoers file"
template = "page.html"
date = 2024-02-13T21:27:00Z
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

ESC,随后:wq 退出即可
