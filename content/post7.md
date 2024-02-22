+++
title = "VB假期作业卷答案"
template = "page.html"
date = 2024-02-21T11:25:00Z
[taxonomies]
tags = ["VB", "临时" ]
[extra]
summary = "占位"
mathjax = "tex-mml"
+++

前言:所有人都是在最后一个星期写作业的。

还在写，别急，写好一题传一题
<br>
然后这里有答案文件以及VB6.0精简版
<br>
[答案文件](http://8.217.107.202:17509)

<details> <summary>点击展开</summary>


<img src= https://img.xwyue.com/i/2024/02/21/65d5a3dfed196.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e00929f.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e0a6b33.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e110efd.png width="40%">
<img src= https://img.xwyue.com/i/2024/02/21/65d5a3e224313.png width="40%">
<img src= https://www.pnglog.com/Uwlc0v.jpg width="20%">
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

---

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

---

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

---

## 第九题-电话计费

### 题目要求：

![1708517371343.png](https://img.xwyue.com/i/2024/02/21/65d5e7ff22c18.png)

### 示例答案：

不会   等陈老师回复，会的私信我一下

---

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

---

## 第十一题-成绩奖励

### 题目要求：

![](https://img.erpweb.eu.org/imgs/2024/02/637e27898765833d.png)

### 示例答案：

图片实在看不清..  不管了 就这样写吧

![](https://img.erpweb.eu.org/imgs/2024/02/bca30b306352b0af.png)

```VB
Private Sub Command1_Click()
Dim a As Integer
a = Val(Text1.Text)

Select Case a
   Case 6 To 8
      MsgBox "第" & a & "月，是夏季", vbOKOnly, "判断"
   Case 9 To 11
      MsgBox "第" & a & "月，是春季", vbOKOnly, "判断"
   Case 12, 1, 2
      MsgBox "第" & a & "月，是冬季", vbOKOnly, "判断"
   Case 3 To 5
      MsgBox "第" & a & "月，是秋季", vbOKOnly, "判断"
   Case Else
      MsgBox "所输入不属于月份", vbOKOnly + vbExclamation, "错误"
End Select



End Sub
```

---

## 第十二题-托运计费

### 题目要求：

![](https://img.erpweb.eu.org/imgs/2024/02/c68d32fb3fbceb39.png)

### 示例答案：

![](https://img.erpweb.eu.org/imgs/2024/02/4dd071091b6ea855.png)

```VB
Private Sub Command1_Click()
Dim a As Single, p As Single
   a = Val(Text1.Text)
If a > 0 And a <= 50 Then
   p = 0.3 * a
ElseIf a > 50 Then
   p = 0.3 * 50 + 0.6 * (a - 50)
Else
   MsgBox "请输入正确的数值!", vbOKOnly + vbExclamation, "错误"
End If
Text2.Text = Str(p)
End Sub
Private Sub Command2_Click()
   End
End Sub
```

---

## 第十三题-计算器

### 题目要求：

![1708522748046.png](https://www.pnglog.com/HmbN7U.png)

### 示例答案：

![1708523267616.png](https://www.pnglog.com/X6d8pY.png)

```
Private Sub Command1_Click()
Dim a As Single, b As Single, c As Single
   a = Val(Text1.Text)
   b = Val(Text2.Text)

If Text3.Text = "/" Then
   c = a / b
ElseIf Text3.Text = "\" Then
   c = a \ b
ElseIf Text3.Text = "+" Then
   c = a + b
ElseIf Text3.Text = "-" Then
   c = a - b
ElseIf Text3.Text = "*" Then
   c = a * b
Else
   MsgBox "请输入正确的内容！", vbOKOnly + vbExclamation, "错误"
End If
End Sub

Private Sub Command2_Click()
   Text1.Text = ""
   Text2.Text = ""
   Text3.Text = ""
   Text4.Text = ""
End Sub

Private Sub Command3_Click()
   End
End Sub
```


睡觉 2024/2/21 22:15

---

醒了  现在动  2024/2/22  10:21

## 第十四题-计算结果

### 题目要求：

![1708569638473.png](https://www.pnglog.com/baCzfD.png)

### 示例答案：

![1708570090390.png](https://www.pnglog.com/4sHG27.png)

```VB
Private Sub Command1_Click()
Dim a As Integer, i As Integer, j As Single
   a = 1
For i = 1 To 99 Step 2
   j = j + a / i
   a = -a
Next i
 Print "s=    " & j
End Sub

Private Sub Command2_Click()
   End
End Sub
```

## 第十五题-求公约数

### 题目要求：

![1708570194960.png](https://www.pnglog.com/3oUNra.png)

### 示例答案：

![1708571211678.png](https://www.pnglog.com/XctGVd.png)

```VB
Private Sub Command1_Click()
Dim a As Integer, i As Integer, c As Integer
    a = Val(Text1.Text)

For i = 1 To a
  If i / 3 = Fix(i / 3) And i / 5 = Fix(i / 5) Then
    Text2.Text = Text2.Text & Str(i)
    c = c + 1
  End If
Next i
    Text3.Text = Str(c)
End Sub
```

注意!!把自动换行打开!!

---

## 第十六题-求奇偶和

### 题目要求：

![1708571419028.png](https://www.pnglog.com/uuTPGl.png)

//我猜按钮2是退出...      不知道

### 示例答案：

![1708571843469.png](https://www.pnglog.com/lXXV6A.png)

```VB
Private Sub Command1_Click()
Dim i As Integer, o As Integer, j As Integer
 For i = 1 To 100
   If i / 2 = Fix(i / 2) Then
     o = o + i
   Else
     j = j + i
   End If
 Next i
Text1.Text = Str(j)
Text2.Text = Str(o)
End Sub

Private Sub Command2_Click()
   End
End Sub
```

---

## 第十七题-求公约数

### 题目要求：

![1708571908582.png](https://www.pnglog.com/0bz6Cc.png)

字符个数可能是字母个数。

### 示例答案：

![1708573154858.png](https://www.pnglog.com/L1tC6Y.png)

```VB
Private Sub Command1_Click()
Dim a As String
    a = Text1.Text
For i = 1 To Len(a)
    b = Mid(a, i, 1)
  If b = " " Then
    kg = kg + 1
  ElseIf Asc(b) >= 48 And Asc(b) <= 57 Then
    sz = sz + 1
  ElseIf Asc(b) >= 65 And Asc(b) <= 97 Then
    zf = zf + 1
  Else
    qt = qt + 1
  End If
Next i

Text2.Text = zf
Text3.Text = kg
Text4.Text = sz
Text5.Text = qt


End Sub
```

![1708574819098.png](https://www.pnglog.com/Lvy2Sx.png)

我丢工程了...写好的给我发一份，谢谢

---

## 第十八题-计平均分

### 题目要求：

![1708574898723.png](https://www.pnglog.com/ElajVc.png)

### 示例答案：

![1708575720526.png](https://www.pnglog.com/uuWegr.png)

```VB
Private Sub Command1_Click()
Dim rs As Integer, a As Single, pfj As Single, zf As Single, bjg As Integer
 rs = 1
 Do
 a = InputBox("请输入第" & rs & "个学生的成绩", "成绩录入")
    If a < 0 Then
      Exit Do
    Else
      zf = zf + a
      rs = rs + 1
    End If
    If a < 60 Then
       bjg = bjg + 1
    End If
 Loop
pfj = zf / rs

Text1.Text = pfj
Text2.Text = bjg

End Sub
```

## 第十九题-年龄问题

### 题目要求：

![1708577160269.png](https://www.pnglog.com/HtyQm4.png)

//我没有幼圆  自行设置！！！

### 示例答案：

![1708577077955.png](https://www.pnglog.com/xfqfp1.png)

## 第二十题-多少棵树

### 题目要求：

![1708577287785.png](https://www.pnglog.com/c5PZg7.png)

### 示例答案：

![1708577726517.png](https://www.pnglog.com/RyRse2.png)

```VB
Private Sub Command1_Click()
Dim xm As Integer, s As Integer, y As Integer
 xm = 17
 y = 3
 s = 3
Do Until s >= 100
    xm = xm + 1
    y = y + 2
    s = s + y
Loop

Label1.Caption = "到" & Str(xm) & "岁共种到了" & Str(s) & "棵树"


End Sub
```

</font>
</font>
