# this file is a description for the project

GCC : The GNU Compiler Collection

GDB : The GUN project debugger

./vscode/tasks.json  这个文件是用来配置代码的编译工具的，比如code runner

./vscode/c_cpp_properties.json 是用来配置c语言和c++的相关配置，比如头文件或别的内容

gcc -g 加个-g 是为了gdb 用，不然gdb用不到

gcc -g file_name -o some | some  来执行两个步骤，|之前编译代码，之后执行代码

gcc 编译器是用4个字节存储整数的

## C语言类型

一、基本类型 
1、整形类型：int ,short int,long int,long long int(C99),char,bool
2、浮点类型：float ,double,双精度浮点型(float_complex,double_complex,long long_comples)
二、枚举类型 enum
三、空类型 void
四、派生类型 
1、指针类型 *
2、数组类型 []
3、结构体类型 struct
4、共用体类型 union
5、函数类型

## 指针

变量名是什么？指针是什么？
变量名是地址的别名，而指针就是地址本身，可以直接操作内存地址，进行加减等，但是变量名没有这样的能力，他只能使用变量的值，如果和获取变量对应的指针？使用&varname 就可以获取到指针。变量是直接访问，指针是间接访问。

## 机器语言 指令系统

计算机不能识别人类的语言，她只能识别二进制信息，在计算机产生的初期，人们为了让计算机工作，必须编写由0和1组成的一系列指令，通过他指挥计算机工作，在研制计算机时，需要先设计该型号计算机的指令系统，规定一条由若干0和1组成的指令使得计算机可能产生特定的操作/行为，一个型号机器的指令的集合称为该计算机的机器语言。机器语言是紧密依赖于计算机的硬件的，不同型号的计算机的机器语言是不一样的，难以编写通用和可扩展的程序。

## 编译系统

显然使用高级语言编写的代码计算机是无法识别的，必须事先把高级语言编写的程序翻译成机器语言程序，这个翻译工作就是由编译系统的软件来实现的。

## 位，字节，地址

位：又称比特，每一个二极管元件成为一个二进制位，是存储信息的最小单位，他的值是0或1

字节：又称为“拜特”，一个存储器包含很多二进制位，如果直接使用位来管理和表示很不方便，一般将八个二进制位组织成一组，成为字节，这是人们最常使用的单位。

地址：操作系统把所有的存储单元以字节为单位编号，比如 2001-2002-2003-2004-2005--- 以此类推，可能在2001这个存储单元中存储的是一个字符'a'或是别的内容，这样操作系统就能够根据编号找到对应的存储单元了。指针指的就是这些编号地址，指针变量就是用来保存这些编号的。变量名用来表示存储单元，通过 &varname操作可以得到变量的指针(整个变量所占据的内存块的首地址)。

'*'作为指针操作运算符时候 是从右到左的结合的。

赋值运算符都是从右到左的运算规则 = *= += -=等等,在加上赋值运算符返回被赋的值，所以可以这样写代码 a=b=10;

如果要输出中文，那么在编译的时候加上这个参数 -fexec-charset=GBK

## C语言关键字作用说明

* typedef 定义类型别名,它用来定义新的类型别名,比如
    typedef int Length; 此时你就可以使用Length定义变量了，他和int没什么区别
    typedef char *String; 这样就可使用String表示字符串
    ```C
    typedef struct tnode *TreePtr; //TreePtr 是 (struct tnode *) 的别名
    typedef struct tnode
    {
        int data;
        TreePtr leftChild;
        TreePtr rightChild;
    } TreeNode; //TreeNode 是 (struct tnode) 的别名
    ```