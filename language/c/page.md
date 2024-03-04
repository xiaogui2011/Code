# Page

### C语言搭建环境

1. 下载clion
2. compilers and the make utility
3. `xcode-select --install`
4. it is not necessary for CLion to install the full package of Xcode.
5. check version of xcode installed default `clang --version`
6. When find `invalid active developer path during project loading in CLion`重新安装即可解决 `xcode-select --intstall`
7.

### 第三天

#### 05 第一个代码分析

main函数由系统**自动**调用，不需要人为调用

```c
# include<stdio.h>
int main(int argc, char const *argv[])
{
	/* code */
	return 0;
}
```

linux C函数手册

通过man手册查看 `man 3 printf`

`vim /usr/include/stdio.h`

标准的头文件使用**尖括号**`< >` **自定义**的头文件使用**引号**`""`

#### 06 代码分析总结

qt creater

有些**头文件**在某个编译器里可以不需要

#### 07 windows gcc 编译代码

mingw492\_32

linux下`gcc`编译的可执行程序不带`exe`， 在windows下运行无需`./`

#### 08 windows gcc 编译代码

gcc是一个编译器

.c 和 .cpp区别

二进制代码有时候是乱码

gcc warning 不会影响编译

代码一样，只是对应平台的编译器不同。

Windows 向下兼容

Linux 不向下兼容

#### 09 system调用命令

常用的头文件

`string.h`字符串处理

`stdio.h`输入输出

`stdlib.h` 动态分配空间

linux上所有的命令都是c语言写的一个程序，运行命令不需要加`./`

system("ls");

在已经运行的程序中，执行另一个外部程序

c语言的库函数调用，不能保证**执行结果**是一样的，同样的库函数在不同的OS下执行结果可能是**不一样的**

中文才有**编码问题**，linux默认的 中文编码是utf-8(也就是Unicode)

calc

windows框架`QT`和`MFC`

`头文件`就像是Python的中的`包`

####
