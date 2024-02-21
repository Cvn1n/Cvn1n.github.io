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

-------------------------------------------------------------------------------------------------------------

## 第二题-窗体切换

### 题目要求：

![](https://img.erpweb.eu.org/imgs/2024/02/2b12fb8426bbf588.png)

// I   上图所示窗体排列中，控件按钮从左往右依次为:1.返回窗体一 2.加载窗体二  3.显示窗体二  4.退出

// II  窗体左上显示自左往右为：窗体二   窗体一

// III 任务要求如上图所示[共两点]

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

-------------------------------------------------------------------------------------------------------------

## 第三题

### 题目要求：


// I   上图所示窗体排列中，控件按钮从左往右依次为:1.返回窗体一 2.加载窗体二  3.显示窗体二  4.退出

// II  窗体左上显示自左往右为：窗体二   窗体一

// III 任务要求如上图所示[共两点]

### 示例答案：


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

</font>
</font>

