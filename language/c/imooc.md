# imooc

```
《Linux C语言编程基本原理与实践》
友情链接： http://www.imooc.com/view/248 

《Linux C语言指针与内存》
友情链接： http://www.imooc.com/view/394

《Linux C语言结构体》
友情连接： http://www.imooc.com/view/409

《C语言学习攻略》
友情连接： http://www.imooc.com/course/programdetail/pid/37
```

## [Linux C语言编程基本原理与实践](https://www.imooc.com/learn/248)

### C语言 ARM嵌入式

### C语言 单片机

### C语言 Arduino

[**Where \<stdio.h> is located in System?**](https://www.quora.com/Where-stdio-h-is-located-in-System)

> `/usr/include/stdio.h` 标准输入输出库

[**Tab key == 4 spaces and auto-indent after curly braces in Vim**](https://stackoverflow.com/questions/234564/tab-key-4-spaces-and-auto-indent-after-curly-braces-in-vim)

> _fileName `.vimrc`_

```
filetype plugin indent on
" show existing tab with 4 spaces width
set tabstop=4
" when indenting with '>', use 4 spaces width
set shiftwidth=4
" On pressing tab, insert 4 spaces
set expandtab
```

**vim**

`:sp`新建一个文件，并且之前的文件不删除 `ctrl w 下`切换文件

~~**如何编译两个源代码**~~

**源文件 -> 多个代码**

调用一个包内的其他函数，依然遵循`先定义，后使用`的规范。不能因为gcc智能化而忽略代码的健壮性。 所以：声明语句：`# inclue "max.c"`

* 声明的区别
  1. 尖括号`<>`代表预装的库，编译的时候，gcc会去系统目录和环境变量下查找
  2. 引号`""`代表，通常是相对路径的。
* notes
  1. 头文件一般是以`.h`结尾的文件
  2. 而上述代码`# inclue "max.c"` 相当于把整个max函数源代码复制进来了，`所以不需要编译`否则报错出现了两次。
  3. 所以编译的时候，只需要编译一个文件`包换main函数的文件`

**定义和声明分离**

分开编译：`gcc -c a.c -o a.o`

* a.o只要编译后，可以被无数次的使用

编译后做链接操作：

```
gcc a.o hello.c
```

### 静态库

**`.o文件`的缺点**

如果别人将自己编写的`.c`文件使用gcc编译成`.o`的静态库以后，那么调用者无法查看编写的源代码

```
cat a.o 
// 结果是一堆乱码。
```

**引出了`.h`头文件**

**头文件(.h)就是调用了.c文件的函数，然后main用预处理指令加载头文件`import "max.h"`即可使用**

_a.h_ :

```
int min(int a, int b)
```

头文件只需要声明就可以

.c编译成.o文件，实际上执行的指令都在这个.o文件里

**`makefile的编写`**

`使用场景`是什么：成千上万个.c文件需要`gcc -c *.c -o xxx.o`

**6个空格**而不是**4个空格**

```
# this is make file
hello.out:max.o min.o hello.c
      gcc max.o min.o hello.c
max.o:max.c
      gcc -c max.c
min.o:min.c
      gcc -c min.c
```

递归寻找需要的以来文件

* 曾经编译过的文件，再次编译的时候就可以节约时间了

**make & make install**

* make工具可以将大型的开发项目分成若干个模块
* make工具很清晰和很快捷的整理源文件
* gcc 对于大型项目是不合理和不可行的。虽然：make内部也是用的gcc。

[**`makefile:4: *** missing separator. Stop`**](https://stackoverflow.com/questions/16931770/makefile4-missing-separator-stop)

> makefile has a very `stupid relation with tabs`, all actions of every rule are identified by tabs ...... and No 4 spaces don't make a tab, only a tab makes a tab...

[**`warning: implicit declaration of function`**](https://stackoverflow.com/questions/8440816/warning-implicit-declaration-of-function)

> You are using a function for which `the compiler has not seen a declaration` ("prototype") yet.

### makefile 和 连接文件
