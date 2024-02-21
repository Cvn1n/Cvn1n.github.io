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

前言:所有人都是在最后一个星期写作业的。

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

```VB
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

```VB
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

```VB
Private Sub Command1_Click()
   Form2.Hide
   Form1.Show
End Sub
```

---

## 第三题-文本编辑器

### 题目要求：

![](https://i.miji.bid/2024/02/21/32337371e9e4268bdd06d7a1b4813024.png)

// I   上图所示窗体排列中，控件按钮自上往下依次为： 复制 剪切 粘贴  隶书 楷体 宋体

// II  窗体左上显示为：简单文本编辑器

// III 任务要求如上图所示

### 示例答案:

![1708511786255.png](https://img.xwyue.com/i/2024/02/21/65d5d23089700.png)
(使用一个变量A来代替剪切板)

```VB
Dim a As String

Private Sub Command1_Click()
   a = Text1.SelText
End Sub

Private Sub Command2_Click()
   a = Text1.SelText
   Text1.SelText = ""
End Sub

Private Sub Command3_Click()
   Text1.SelText = a
End Sub

Private Sub Command4_Click()
   Text1.Font.Name = "隶书"
End Sub

Private Sub Command5_Click()
   Text1.Font.Name = "楷体"
End Sub

Private Sub Command6_Click()
   Text1.Font.Name = "宋体"
End Sub
```

---

## 第四题-文本框练习

### 题目要求：

![1708502417778.png](https://img.xwyue.com/i/2024/02/21/65d5ad960dc35.png)

// I   窗体左上显示为：文本框练习

// II  文本框名字有要求!

// III 任务要求如上图所示

### 示例答案：

![1708502821892.png](https://img.xwyue.com/i/2024/02/21/65d5af2ace620.png)

```VB
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

```VB
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

---

## 第六题-计算圆的周长面积

### 题目要求：

![1708504121757.png](https://img.xwyue.com/i/2024/02/21/65d5b43dd626d.png)

### 示例答案：

![1708504634238.png](https://img.xwyue.com/i/2024/02/21/65d5b64146c00.png)
![1708504664600.png](https://img.xwyue.com/i/2024/02/21/65d5b65c8b473.png)

```VB
**Private Sub Command1_Click()
Dim a As Single, b As Single, c As Single
   a = Val(Text1.Text)
   b = a * 2 * 3.14
   c = a * a * 3.14
   
Label2.Caption = "当圆的半径为" & Str(a) & "时," & vbCrLf & "周长为" & Str(b) & vbCrLf & "面积为" & Str(c)
End Sub
**
```

## 第七题-判断三角形

### 题目要求：

![1708504773452.png](https://img.xwyue.com/i/2024/02/21/65d5b6ceb2654.png)

### 示例答案：

![1708505730268.png](https://img.xwyue.com/i/2024/02/21/65d5ba866c30e.png)

```VB
Private Sub Command1_Click()
Dim a As Single, b As Single, c As Single, p As Single, s As Single
   a = Val(InputBox("请输入三角形第一条边", "三角形数据录入"))
   b = Val(InputBox("请输入三角形第二条边", "三角形数据录入"))
   c = Val(InputBox("请输入三角形第三条边", "三角形数据录入"))

If a + b <= c Or a + c < b Or b + c < a Then
   MsgBox "所输入三边无法构成三角形,请重新输入", vbOKOnly + vbExclamation, "错误"
Else
   p = (a + b + c) / 2
   s = Sqr(p * (p - a) * (p - b) * (p - c))
   MsgBox "所录入三角形面积为：" & Str(s), vbOKOnly, "结果"
End If
End Sub
```

## 第八题-逆序输出

### 题目要求：

![1708506421514.png](https://img.xwyue.com/i/2024/02/21/65d5bd3b4223e.png)

### 示例答案：

![1708512597327.png](https://img.xwyue.com/i/2024/02/21/65d5d55a69525.png)

```VB
Private Sub Command1_Click()
Dim a As Integer
   Randomize
   a = Int(Rnd * ((999 - 100 + 1) + 100))
   Text1.Text = Str(a)
End Sub

Private Sub Command2_Click()
Dim b As Integer
Text2.Text = ""
b = Len(Text1.Text)
For i = b To 1 Step -1

Text2.Text = Text2.Text & Mid(Text1.Text, i, 1)

Next i
   
End Sub
```

## 第九题-电话计费

### 题目要求：

![1708517371343.png](https://img.xwyue.com/i/2024/02/21/65d5e7ff22c18.png)

### 示例答案：

不会   等陈老师回复，会的私信我一下

## 第十题-成绩奖励

### 题目要求：

![1708519128023.png](https://img.xwyue.com/i/2024/02/21/65d5eededdcd1.png)

### 示例答案：

![](https://img.erpweb.eu.org/imgs/2024/02/5b1f31baf4f5eaee.png)

```VB
Private Sub Command1_Click()
Dim a As Single, b As Single, c As Single

If a + b + c > 285 Then
   Label4.Caption = "可以奖励"
ElseIf a > 90 And b > 90 And c > 90 Then
   Label4.Caption = "可以奖励"
ElseIf a > 90 And b > 90 And c > 90 Then
   Label4.Caption = "可以奖励"
ElseIf a = 100 And b = 100 And c > 80 Then
   Label4.Caption = "可以奖励"""
Else
   Label4.Caption = "不可以奖励"
End if
End Sub

Private Sub Command2_Click()
   End
End Sub
```

</font>
</font>
