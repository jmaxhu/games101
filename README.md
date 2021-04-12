# GAMES101 学习笔记

大家都说[闫令琪老师](https://sites.cs.ucsb.edu/~lingqi/)的[现代计算机图形学入门](https://sites.cs.ucsb.edu/~lingqi/teaching/games101.html)讲得非常好，很适合初学者学习。自己也想学习计算机图形学方面的知识，所以就边学边做笔记，希望自己理解得更加深刻。

该笔记主要以做课后作业的方式完成。所以要先配置程序编译环境。本人用的是 macOS 系统，所以相应的也记录下在 macOS 下的环境配置。

## macOS 环境配置

作业使用 C++ 编写，并使用 [CMake](https://cmake.org/) 作为编译工具。所以首先需要安装 CMake，在 mac 下安装软件的最佳方式就是 [Homebrew](https://brew.sh/index_zh-cn)，如果你还没安装 homebrew，请先根据官网提示安装。
由于国内网络方式的原因，用 homebrew 安装软件会比较慢，所以请配置[国内镜像](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/).

### 安装 VS Code

从[官网](https://code.visualstudio.com/)下载并安装 VS Code。并安装[C/C++扩展](https://github.com/microsoft/vscode-cpptools), [CMake工具扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools)

### 安装 CMake

```shell
brew install cmake

# 验证
cmake --version
# 输出: cmake version 3.14.0
```

### 安装 Eigen库

[Eigen](https://eigen.tuxfamily.org/index.php)是该课程使用的一个C++的线性代数模板库。每个作业都会用到，所以要先安装。我安装的版本是3.3.9。

```shell
brew install eigen

# 验证: 安装后会在 /usr/local/include 目录下多一个文件夹链接 eigen3。如果没有则可以手动执行以下命令：
# brew link --overwrite eigen
```

## 课程目录

1. 计算机图形学概述

   * [学习视频](https://www.bilibili.com/video/av90798049)
   * [课件](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_01.pdf)

2. 向量与线性代数
   * [学习视频](https://www.bilibili.com/video/BV1X7411F744?p=2)
   * [课件](https://sites.cs.ucsb.edu/~lingqi/teaching/resources/GAMES101_Lecture_02.pdf)
   * [作业链接](http://games-cn.org/forums/topic/graphics-intro-hw0/)
   * [作业笔记](./hw0/README.md)
