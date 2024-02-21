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

## 第二题

### 题目要求：

### 示例答案：
