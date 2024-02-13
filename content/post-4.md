+++
title = "Windows环境下通过LLaMA-Factory微调ChatGLM2-6B模型"
template = "page.html"
date = 2024-02-13T21:27:00Z
[taxonomies]
tags = ["教程", "自然语言处理"]
[extra]
summary = "玩的开心"
mathjax = "tex-mml"
+++


# Windows环境下通过LLaMA-Factory微调ChatGLM2-6B模型

嘛——我永远是个与时代脱轨的人。
<br>
这是上一年的东西了
<br>
想捏角色，所以就来玩玩

本教程适用于  windows环境通过LLaMA-Factory微调ChatGLM2-6B模型

## 关于ChatGLM3-6B

### **硬件需求**

| 量化等级     | 最低GPU(对话) | 最低GPU(微调) |
| -------------- | --------------- | --------------- |
| FP16（标准） | 13GB          | 14GB          |
| INT8         | 8GB           | 9GB           |
| INT4         | 6GB           | 7GB           |

### **介绍**

> [ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B)是由清华大学KEG实验室和智谱AI联合开源的、基于GLM架构（ChatGPT是基于GPT架构）、支持中英双语的对话语言模型。它拥有62亿参数（也是其名称中6B的来源，这两方之前也开源了参数更大的ChatGLM-130B模型），并且针对中文问答和对话进行了专门优化。
<br>
> 而 [ChatGLM2-6B](https://github.com/THUDM/ChatGLM2-6B)是开源中英双语对话模型 [ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B) 的第二代版本，在保留了初代模型对话流畅、部署门槛较低等众多优秀特性的基础之上，[ChatGLM2-6B](https://github.com/THUDM/ChatGLM2-6B) 增加了不少性能，具体可以去github看。
<br>
> ————————————————
<br>

1.该模型目前最适合中文训练
> <br>
2.该模型有思想钢印
<br>
3.6B体量有限 具有局限性

## ## ## 详细步骤详细步骤

### 一、环境准备

#### 环境1-[CUDA](https://so.csdn.net/so/search?q=CUDA&spm=1001.2101.3001.7020)

ask:"为什么要安装这个?"
<br>
这个架构可以让显卡更好的处理深度学习的计算
<br>
几乎所有深度学习框架都首选cuda作为底层加速库
<br>
ChatGLM也不例外

ask:"在哪下载"
<br>
可以直接去官网：[CUDA Toolkit 12.3 Update 1 Downloads | NVIDIA Developer](https://developer.nvidia.com/cuda-downloads "CUDA Toolkit 12.3 Update 1 Downloads | NVIDIA Developer")

#### 环境2-安装Python 3.10以上版本

chatglm需要Python 3.10以上版本
<br>
下载安装Python：[Python官网](https://www.python.org/downloads/)

#### 环境3- 安装anaconda配置python环境

下载安装anaconda：[清华大学开源镜像网站](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/ "Index of /anaconda/archive/ | 清华大学开源软件镜像站 | Tsinghua Open Source Mirror")
<br>
一路Next到底就好

安装完成后在系统环境变量中找到Path，新建 如下图所示，确定
<br>
[![pF8D0de.md.png](https://s11.ax1x.com/2024/02/13/pF8D0de.md.png)](https://imgse.com/i/pF8D0de)

路径\Anaconda
<br>
路径\Anaconda\Scripts
<br>
路径\Anaconda\Library\bin
<br>
路径\Anaconda\Library\mingw-w64\bin
<br>
路径\Anaconda\Library\usr\bin
<br>

### 二、获取模型

如果你没有Git，先去安装下吧
<br>
```
git clone https://github.com/THUDM/ChatGLM3.git
```
<br>
然后使用 pip 安装依赖：
<br>
```
pip install -r requirements.txt
```
<br>
(这个命令会自动根据它们提供的requirements.txt安装chatglm需要的东西)

### 三、配置模型的环境变量

到系统环境变量
<br>
在系统变量中分别新建下面(路径自己改到正确的!!)

变量名：MODEL_PATH
<br>
变量值：模型的根目录路径
<br>
(示例D:\CHAGML\ChatGLM3)

变量名：IPYKERNEL
<br>
变量值：chatglm3-demo

### 四、获取ChatGLM3的训练模型

ChatGLM3目录下开cmd窗口

```
git lfs install
git clone https://huggingface.co/THUDM/chatglm3-6b
```


### 五、安装启动LLaMA-Factory

找个位置，新建文件夹，文件夹下开cmd

```
clone https://github.com/hiyouga/LLaMA-Factory.git
conda create -n llama_factory python=3.10
conda activate llama_factory
cd LLaMA-Factory
pip install -r requirements.txt
```

之后每次启动 从LLaMA-Factory所在的文件夹下 开CMD
<br>
执行下面两条即可

```
conda activate llama_factory
python src/train_web.py
```

运行后，可以通过访问网页使用。

## 最后

//如果你不知道如何自定训练数据，LLaMA-Factory\data下有很多数据文件夹，可以提供参考
<br>
//玩得开心

-------------------------------

最新更新于 2024/2/13

