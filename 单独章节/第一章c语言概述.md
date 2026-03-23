# C 语言基础篇 第一章 精简笔记

## 一、C 语言概述

1.本质：人与计算机的交流语言，遵循语法规则，计算机无条件服从。

2.特点：优点为代码量小、执行快、功能强、编程自由；缺点为开发周期长、可移植性差、易出错、依赖平台库。

3.学习价值：理工科必修课、面试必备，是底层开发及其他语言（Java/C++ 等）的基础。

4.应用领域：操作系统 / 驱动、嵌入式、高性能服务（Apache/Nginx）、数据库、编译器等。

5.简洁性：32 个关键字、9 种控制语句、34 种运算符，可实现复杂功能。

## 二、第一个 C 程序：HelloWorld

1.源代码

2.源文件规范：扩展名必须为.c。

3.gcc 编译器：

作用：将高级语言转为机器语言，跨平台且支持多语言。

常用命令：gcc 源文件.c -o 可执行文件，核心选项：-o（指定输出名）、-E（预处理）、-S（编译）、-c（汇编）。

4.Windows gcc 配置：

找到 Qt 集成的 gcc 路径（如C:\\Qt\\Qt5.5.0\\Tools\\mingw492_32\\bin）。

配置环境变量：将路径追加到系统 Path 中。

测试：cmd 输入gcc无报错即成功。

5.编译运行：

默认编译：gcc hello.c，生成a.exe。

指定文件名：gcc hello.c -o hello，生成hello.exe，直接输入文件名执行。

6.代码解析：

##### include <stdio.h>：包含头文件，printf函数依赖此文件；<>从系统目录查找头文件，""先查当前目录。

main()：程序唯一入口，有且仅有一个。

printf("hello world\\n")：输出字符串，\\n表示回车换行。

return 0：程序执行成功返回 0，失败返回 - 1。

## 三、system 函数

头文件：#include <stdlib.h>。

功能：在当前程序中执行外部命令。

平台差异：Windows 用system("calc")（打开计算器），Linux 用system("ls")（查看目录）。

## 四、C 语言编译过程

四步流程：

预处理：展开头文件、宏定义，删除注释，不检查语法。

编译：检查语法，生成汇编文件（.s）。

汇编：生成二进制目标文件（.o）。

链接：链接库文件，生成可执行文件。

分步编译命令：

预处理：gcc -E hello.c -o hello.i。

编译：gcc -S hello.i -o hello.s。

汇编：gcc -c hello.s -o hello.o。

链接：gcc hello.o -o hello。

## 五、集成开发环境 IDE

Qt Creator（跨平台）：

核心快捷键：Ctrl+i（格式化）、Ctrl+/（注释）、F4（.h/.cpp 切换）、F9（断点）、F5（调试）。

Microsoft Visual Studio（Windows）：

核心快捷键：Ctrl+k+f（格式化）、Ctrl+F5（不调试运行）。

解决 C4996 错误：在.c 文件首行添加#define \_CRT_SECURE_NO_WARNINGS。

## **六、思维导图**

