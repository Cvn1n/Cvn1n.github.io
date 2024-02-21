+++
title = "VB假期作业卷答案"
template = "page.html"
date = 2024-02-21T11:25:00Z
[taxonomies]
tags = ["VB", "临时" ]
[extra]
summary = "答案"
mathjax = "tex-mml"
+++

前言:    所有人都是在最后一个星期写作业的。

<details> <summary>点击展开</summary>

<img src= https://img.xwyue.com/i/2024/02/21/65d5a3dfed196.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e00929f.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e0a6b33.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e110efd.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e224313.png width="40%">

</details>

---

<font color=black>
<font face = "微软雅黑">

# Visual Basic 编程作业卷

## 第一题-窗体测试

### 题目要求：

![](https://img.erpweb.eu.org/imgs/2024/02/61c5bc00054676c7.png)

// I   控件按钮从左往右依次为:1.输出文字  2.清除文字 3.加载背景图片 4.去除背景 5.退出

// II  窗体左上方显示为：窗体测试

// III 任务要求如上图所示[共六点]

### 示例答案：

![](https://img.erpweb.eu.org/imgs/2024/02/ee0dc4b10f39237d.png)

```VB1
Private Sub Form_Load()
   Form1.BackColor = vbYellow
   Form1.Font.Size = 25
   Form1.ForeColor = vbRed
   Form1.Font.Name = "隶书"
End Sub

Private Sub Command1_Click()
   Print "窗体属性、方法、事件的运用；"
   Command2.Enabled = True
End Sub

Private Sub Command2_Click()
   Cls
   Command2.Enabled = False
End Sub

Private Sub Command3_Click()
   Picture1.Picture = LoadPicture("test.jpg")
End Sub

Private Sub Command4_Click()
   Picture1.Picture = LoadPicture("")
End Sub

Private Sub Command5_Click()
   End
End Sub
```

---

## 第二题-窗体切换

### 题目要求：

![](https://img.erpweb.eu.org/imgs/2024/02/2b12fb8426bbf588.png)
![](https://i.miji.bid/2024/02/21/ca9fb778eb3147ca6350acd37b3b96f6.png)

// I   上图所示窗体排列中，控件按钮从左往右依次为:1.返回窗体一 2.加载窗体二  3.显示窗体二  4.退出

// II  窗体左上显示自左往右为：窗体二   窗体一

// III 任务要求如上图所示[共四点]

### 示例答案：

![](https://img.erpweb.eu.org/imgs/2024/02/7e84382ac5e0c3e9.png)

关于窗体一部分

```vb2-1(2)
Private Sub Command1_Click()
   Load Form2
   Print "窗体二已被加载"
End Sub
Private Sub Command2_Click()
   Form2.Show
   Form1.Hide
End Sub
Private Sub Command3_Click()
   End
End Sub
```

关于窗体二部分

```VB2-2(2)
Private Sub Command1_Click()
   Form2.Hide
   Form1.Show
End Sub
```

---

## 第三题-文本编辑器[待补充]

### 题目要求：

![](https://i.miji.bid/2024/02/21/32337371e9e4268bdd06d7a1b4813024.png)

// I   上图所示窗体排列中，控件按钮自上往下依次为： 复制 剪切 粘贴  隶书 楷体 宋体

// II  窗体左上显示为：简单文本编辑器

// III 任务要求如上图所示

### 示例答案：

跳过  不会，  问陈老师了还没回复

有答案的给我来一份

我知道怎么选中 剩下的 教过的里面想不到有什么东西。

---

## 第四题-文本框练习

### 题目要求：

![1708502417778.png](https://img.xwyue.com/i/2024/02/21/65d5ad960dc35.png)

// I   窗体左上显示为：文本框练习

// II  文本框名字有要求!

// III 任务要求如上图所示

### 示例答案：

![1708502821892.png](https://img.xwyue.com/i/2024/02/21/65d5af2ace620.png)

```vb
Private Sub T1_Change()
T2.Text = T1.Text
End Sub
```

---

## 第五题-数字时钟

### 题目要求：

![1708502880250.png](https://img.xwyue.com/i/2024/02/21/65d5af66e429c.png)

// I   热键通过Capiton属性中&+需要的键实现

// II  按钮控件从左到右依次为 开始(热键B)  退出(热键E)

// III 任务要求如上图所示

### 示例答案：

![1708503477455.png](https://img.xwyue.com/i/2024/02/21/65d5b1bb9347c.png)

```vb
Private Sub Command1_Click()
Timer1.Enabled = True
End Sub

Private Sub Command2_Click()
End
End Sub

Private Sub Timer1_Timer()
Label1.Caption = Time
End Sub
```



</font>
</font>
