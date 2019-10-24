---
title: Java基础
date: 2019-10-16 21:39:31
tags:
---

# 一、 Java基础语法

## 1.1 Java运行环境

**01 Java语言发展史**

- 1995年Sun公司发布Java1.0版本

- 2006年发布Java 6版本

- 2009年Oracle甲骨文公司收购Sun公司，并与2011发布Java 7版本

- 2014年发布Java 8版本

- 2017年9月发布Java 9版本

- 2018年3月发布Java 10版本

**02 计算机进制转换**

- 将十进制转换为二进制（辗转相除法）

**03 计算机存储单元**

- 位（bit）：一个数字0或者一个数字1，代表一位
- **字节（Byte）**：每逢8位是一个字节，这是数据存储的最小单位
- 1 Byte = 8 bit
- 1 KB = 1024 Byte
- 1 MB = 1024 KB
- 1 GB = 1024 MB
- 1 TB = 1024 GB
- 1 PB = 1024 TB
- 1 EB = 1024 PB
- 1 ZB = 1024 EB

**04 命令提示符**

打开cmd命令窗口

```
win + r
```

切换到D盘

```
d:
```

进入目录（按Tab快速补全）

```
cd 目录名
```

返回上一个目录

```
cd..
```

返回根路径

```
cd \
```

显示该目录下的文件以及文件夹

```
dir
```

清空屏幕（clean screen）

```
cls
```

退出cmd命令窗口

```
exit
```

**05 Java语言的跨平台性**

- JVM（Java Virtual Machine）：Java虚拟机。**我们编写的Java代码，都运行在JVM上**。

- 跨平台

**06 JDK、JRE与JVM**

- JRE（Java Runtime Environment）：Java程序的运行时环境，包含JVM和运行时环境
- JDK（Java Development Kit）：Java程序开发工具包，包含开发工具和JRE

**07 JDK的下载与安装**

安装的时候，选项中，装了开发工具，可以取消JRE的安装

**08 环境变量的配置**

1. 新建系统变量：JAVA_HOME 变量值：JDK的目录

2. 修改path：添加**%JAVA_HOME%\bin**

## 1.2 HelloWorld案例

**01 HelloWorld的程序代码编写**

- Java程序开发三步骤：**编写、编译、运行**

```
/**
 * Create in by ben by 2019/9/28
 */
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello world");
    }
}
```

**02 HelloWorld程序的编译运行**

编译，会生成一个HelloWorld.class文件

```
javac HelloWorld.java
```

运行

```
Java HelloWorld
```

**03 HelloWorld的常见问题与Nodepad++的使用**

**04 程序注释与HelloWorld说明**

单行注释

```
//
```

多行注释

```
/* */
```

## 1.3 关键字与标识符

**01 关键字的概念与特征**

**02 标识符的概念与规则**

- 标识符

- 命名规则
  
  - 标识符可以包含英文字母26个（区分大小写）、1-9数字、$（美元符号）和_（下划线）

- 命名规范
  
  - 类名规范：首字母大写，后面每个字母首单词大写（大驼峰式）。HelloWorld
  - 变量名规范：首字母小写，后面每个单词首字母大写
  - 方法名规范：同变量名

## 1.4 常量&变量

**01 常量的概念**

- 常量的分类
  1. 字符串常量
  2. 整数常量：
  3. 浮点数常量：直接写上的数字，有小数点
  4. 字符常量：凡是用单引号引起来的单个字符
  5. 布尔常量：true、false
  6. 空常量：null

**02 常量的打印输出**

```
        // 字符串常量
        System.out.println("ABC");
        System.out.println(""); // 字符串两个引号中间的内容为空
        System.out.println("YZ");

        // 整数常量
        System.out.println(122);
        System.out.println(-903);

        // 浮点数常量（小数）
        System.out.println(1.223);
        System.out.println(-3.099);

        // 字符常量
        System.out.println('A');
        System.out.println('猫');
        System.out.println(' '); // 不能为空，要有一个空格

        // 布尔常量
        System.out.println(true);
        System.out.println(false);

        // System.out.println(null); // 错误写法
```

**03 基本数据类型**

四类八种

​    整数型 byte short int long

​    浮点型 float double

​    字符型 char

​    布尔型 boolean

| 数据类型   | 关键字        | 内存占用 | 取值范围                  |
| ------ |:---------- | ---- | --------------------- |
| 字节型    | byte       | 1个字节 | -128~127              |
| 短整型    | short      | 2个字节 | -32768~32767          |
| 整型     | int（默认）    | 4个字节 | -2^31~2^31-1          |
| 长整型    | long       | 8个字节 | -2^63~2^63-1          |
| 单精确浮点数 | float      | 4个字节 | 1.4013E-45~3.4028E+38 |
| 双精确浮点数 | double（默认） | 8个字节 | 4.9E-324~1.7977E+308  |
| 字符型    | char       | 2个字节 | 0~65535               |
| 布尔类型   | boolean    | 1个字节 | true                  |

- 注意事项、
  
  1. 字符串不是基本类型，而是引用类型
  
  2. 浮点型可以只是一个近似值，并非精确的值
  
  3. 浮点范围与字节数不一定相关，例如float的数据范围比long更加广泛，但是float是4字节，long是8字节
  
  4. 浮点数默认double，若使用float类型，需要加上一个后缀F。（F大小写均可）
     
     整数默认int，使用long类型，需要加上后缀L。

**04 变量的概念与定义格式**

**05 变量的基本使用**

**06 变量的注意事项**

1. 如果创建多个变量，那个变量的名称不可重复
2. 对于float和long类型来说，字母后缀F和L不要丢掉
3. 右侧的值不要超过左边的范围
4. 要先赋值，再使用
5. 作用域
6. 可以通过一个语句创建多个变量，但不建议

## 1.5 数据类型转换

**01 数据类型转化_自动转换**

自动类型转换（隐式）

1. 特点：代码不需要进行特殊处理，自动完成

2. 规则：数据范围从小到大

**02 数据类型转化_强制转换**

强制类型转换

1. 特点：代码需要进行特殊的格式处理，不能自动完成
2. 格式：范围小的类型 范围小的变量名 = （范围小的类型） 原本范围大的数据 

**03 数据类型转换_注意事项**

1. 强制类型转换可能会发生精度损失，数据溢出
2. byte/short/char这三种类型都可以发生数学运算，例如加法“+”
3. byte/short/char这三种类型在运算时，首先会提升为int类型
4. boolean类型不能发生数据类型转换

**04 ASCII编码表** 

- A：65
- a：97
- 0：48

ASCII码表：American Standard Code for Information Interchange

Unicode码表：万国码

## 1.6 运算符

**01 算术运算符_四则与取模运算**

|     |     |
| --- | --- |
|     |     |

**02 算术运算符_加号的多种用法**

1. 对于数值来说，那就是加法
2. 对于char类型来说，char会被提升为int，然后再计算
3. 有字符串，结果会变成字符串

**03 算术运算符_自增自减运算符**

**04 赋值运算符**

|      |     |
| ---- | --- |
| `=`  | 等于号 |
| `+=` | 加等于 |
| `-=` | 减等于 |
| `*=` | 乘等于 |
| `/=` | 除等于 |
| `%=` | 取模等 |

**05 比较运算符**

|      |      |
| ---- | ---- |
| `==` | 等于   |
| `<`  | 小于   |
| `>`  | 大于   |
| `<=` | 小于等于 |
| `>=` | 大于等于 |
| `!=` | 不等于  |

**06 逻辑运算符**

|      |       |
| ---- | ----- |
| &&   | 与（并且） |
| \|\| | 或（或者） |
| !    | 非（取反） |

**07 三元运算符**

格式：数据类型 变量名称 = 条件判断 ? 表达式A : 表达式B 

## 1.7 方法入门

**01 方法入门_概念引入**

- 方法就是讲一个功能抽取出来，将代码单独定义在一个大括号内，形成一个单独的功能。

**02 方法入门_方法的定义**

**03 方法入门_方法的调用**

## 1.8 JDK9新特性-Jshell

**01 JDK9的JShell的简单实用**

**02 编译器的两点优化**

编译器会提示一些错误

## 1.9 选择结构-if语句-switch语句

**01 流程概述与顺序结构**

**02 选择结构_单if语句**

```
if(关系表达式){
    语句体；
}
```

**03 选择结构_标准if-else语句**

```
if(关系表达式){
    语句体1；
} else {
    语句体2；
}
```

**04 选择结构_扩展if-else语句**

```
if(判断条件1){
    执行语句1；
} else if(判断条件2){
    执行语句2；
}
...
} else if (判断条件n) {
    执行语句n;
} else {
    执行语句n+1；
}
```

**05 练习**

**06 练习**

**07 选择结构_标准的switch语句**

```
switch(表达式) {
    case 常量值1:
        语句体1;
        break;
    case 常量值1:
        语句体1;
        break;    
    ...
    default:
        语句体n+1；
        break；
}
```

**08 选择结构_穿透的switch语句**

不写break；

## 1.10 迷

## 1.11 开发工具-IDEA

**01 集成开发环境IDE的概述**

**02 IDEA的安装**

**03 IDEA项目结构**

项目包含模块，模块包含多个包，一个包包含多个文件

**04 IDEA的HelloWorld**

**05 IDEA的基本配置**

**06 IDEA的常用快捷键**

| 快捷键              | 功能                         |
| ---------------- | -------------------------- |
| `Alt+Enter`      | 导入包，自动修正代码                 |
| `Ctrl+`Y         | 删除光标所在行                    |
| `Ctrl+D`         | 复制光标所在行的内容，插入到光标下面         |
| `Ctrl+Alt+L`     | 格式化代码                      |
| `Ctrl+/`         | 单行注释，再按取消注释                |
| `Ctrl+Shitf+/`   | 选中代码注释，多行注释，再按取消注释         |
| `Alt+Ins`        | 自动生成代码，toString，get，set等方法 |
| `Alt+Shift+上下箭头` | 移动当前代码行                    |

- 5.fori：五次循环

- 选中一个参数，按`Shift+F6`，修改，所有的相同参数都会被修改

**07 IDEA的项目关闭打开与模**

模块的添加与导入

File ==> Project Structure... ==> Modules ==> + -

## 1.12 方法复习

**01 复习简单方法的使用**

**02 方法的定义格式**

**03 方法的三种调用格式**

1. 单独调用
2. 打印调用
3. 赋值调用

**04 方法的调用流程图解**

**05 对比有参数和无参数**

**06 对比有返回值和无返回值**

**07 方法练习1_比较两个数字是否相等**

**08 方法练习2_求出1到100的累加和**

```
    int getSum(int first, int end){
        int sum = 0;
        for (int i = first; i <= end; i++) {
            sum += i;
        }
        return sum;
    }
```

**09 练习3_打印指定次数的HelloWorld**

**10 方法的注意事项**

- 有返回值时，有且只有一个return

## 1.13 方法重载（Overload）

**01 方法重载的基本使用**

```
    int sum(int a, int b){
        return a+b;
    }
    int sum(int a, int b, int c){
        return a+b+c;
    }

    int sum(int a, int b, int c, int d){
        return a+b+c+d;
    }
```

**02 方法重载的注意事项**

相关

- 参数个数不同
- 或者参数类型不同
- 或者参数的多类型顺序不同

无关

- 与参数名称无关
- 与返回值类型无关

**03 重载练习1_四种不同参数类型的方法**

**04 重载练习2_判断方法的正确重载**

- 方法名区分大小写
- 看方法是否相同，参数个数是否不同，参数顺序是否不同

**05 重载练习3_实现重载的public方法**

- System.out.println();    println实现了重载

## 1.14 数组

**01 数组的概念**

- 数组是一种容器，可以存放多个数据值

数组的特点

1. 数组是一种引用数据类型
2. 数组当中的多个数据，类型必须统一
3. 数组的长度在程序运行期间不可改变

**02 数组的定义格式一：动态初始化**

数据类型[ ] 数组名称 = new 数据类型[数组长度]

```
int[] arrayA = new int[12];
double[] arrayB = new double[3];
String[] arrayC = new String[5];
```

**03 数组的定义格式二：静态初始化**

数据类型[ ] 数组名称 = new 数据类型[ ] {元素1, 元素2, ... };

```
int[] arrayD = new int[]{1,3,4,5};
String[] arrayE = new String[]{"Hello","World"};
```

**04 数组的定义格式三：省略的静态初始化**

数据类型[ ] 数组名称 = {元素1, 元素2, ... };

```
int[] arrayF = {1,3,4,5};
String[] arrayG = {"Hello","World"};
```

- 使用建议：已确认的元素用静态初始化，不确定元素内容的用动态初始化

**05 访问数组元素进行获取**

- 直接打印数组名称，得到的数是内存地址哈希值

```
int a = array[2];
System.out.println(a);
```

**06 访问数组元素进行复制**

- 创建动态数组，
  
  - 整数类型，默认为0
  - 浮点类型，默认为0.0
  - 字符类型，默认为‘\u0000’
  - 布尔类型，默认为false
  - 引用类型，默认为null

- 注意：创建静态数组，也有一个默认值的过程

### **07 Java中的内存划分（5个）**

1. **栈（Strack）**：存放的都是方法中的局部变量。**方法的运行一定要在栈当中运行。**
   
   ​    局部变量：方法的参数，或者是方法{ }内部的变量
   
   ​    作用域：一旦超出作用域，立即从栈内存当中消失

2. **堆（Heap）：凡是new出来的东西，都在堆当中。**
   
   ​    堆内存里面存放的东西都有一个地址值：16进制
   
   ​    堆内存里面的数据，都有默认值。规则：
   
   ​        如果是整数        默认0
   
   ​        如果是浮点数        默认为0.0
   
   ​        如果是字符        默认为‘\u0000’
   
   ​        如果是布尔        默认为false
   
   ​        如果是引用类型    默认为null

3. **方法区（Method Area）**：存储.class相关信息，包含方法的信息。

4. 本地方法栈（Native Method Stack）：与操作系统相关。

5. 寄存器（PC Register）：与CPU相关。

**08 一个数组的内存图**

**09 两个数组的内存图**

**10 两个引用指向同一个数组的内存图**

**11 常见问题：数组索引越界异常**

- 数组的索引编号从0开始，一直到“数组的长度-1”为之

- 如果访问越界元素的时候，索引编号并不存在，就会发生数组索引越界异常ArrayIndexOutOfBoundsException

**12 常见问题：空指针异常**

- 没有赋值，new就好了

**13 获取数组的长度**

​    数组名称.length

- 数组一旦创建，程序运行期间，长度不可改变

**14 数组的遍历输出**

```
int[] array= {1,2,3,34,56,67,23};

for (int i = 0; i < array.length; i++){
    System.out.println(array[i]);
}
```

- 快捷键输出：`array.fori`

**15 求出数组中的最值**

```
    void max(){
        int[] array= {2, 89, 3, 45, -5, 34, 88, 111, 26, 68};
        int max = array[0];
        for (int i = 1; i < array.length; i++){
            if (max < array[i]){
                max = array[i];
            }
        }
        System.out.println("数组的最大值为：" + max);
    }
```

**16 数组元素反转**

```
void xy(){
    int[] array= {2, 89, 3, 45, -5, 34, 88, 111, 26, 68};

    System.out.println("原本的数组：");
    for (int i = 0; i < array.length; i++) {
        System.out.println(array[i]);
    }
    for (int min = 0, max = array.length -1; min < max; min++, max--){
       int temp = array[min];
       array[min] = array[max];
       array[max] = temp;
    }
    System.out.println("反转后的数组：");
    for (int i = 0; i < array.length; i++) {
        System.out.println(array[i]);
    }
}
```

**17 数组作为方法参数_传递地址**

```
    void printArray(int[] array){
        for (int i = 0; i < array.length; i++) {
            System.out.println(array[i]);
        }
    }
```

- 得到的参数是数组array的地址值

**18 数组作为方法返回值_返回地址**

```
int[] computer(int a, int b, int c){
    int sum = a + b + c;
    int svg = a * b * c;
    int[] array = { sum, svg };
    return array;
}
```

# 二、面向对象和封装

## 2.1 描述类介绍与使用

**01 面向对象思想的概述**

​    面向过程：当需要实现一个功能的时候，每一个具体的步骤都要亲力亲为，详细处理每一个细节。

​    面向对象：当需要实现一个功能的，不关心具体的步骤，而是找一个已经具有该功能的人，来帮我做事儿。

**02 面向对象思想的举例**

区别：

- 面向过程：强调过程
- 面向对象：强调对象

特点：三大基本特征

1. 封装
2. 继承
3. 多态

**03 类与对象的关系**

什么是类

- 类：是一组相关**属性**和**行为**的集合
- 属性：
- 行为：

类和对象的关系

- 类是对一类事物的描述，是抽象的
- 对象时一类事物的实例，是具体的
- 类是对象的模板，对象时类的实体

**04 类的定义**

- 成员变量（属性）
- 成员方法（行为）

**05 对象的创建及其使用**

格式：

​    类名称 对象名 = new 类名称();

**06  手机类练习**

**07 一个对象的内存图**

- 成员方法在方法区，调用时需要进栈，调用完出栈，最先调用main方法，也是最后出栈
- 堆存放成员变量以及成员方法的地址值
- new出来的东西都在堆当中

![191014-20：47：41](.\image\191014-20：47：41.png)

**08 两个对象使用同一个方法**

1. 方法区的main方法进栈
2. new一个对象，new出来的东西都在堆当中，堆存放成员变量以及成员方法地址
3. 栈中的new出来的对象存放地址，指向堆中new出来的东西

![191014-21：02：43](.\image\191014-21：02：43.png)

**09 两个引用指向同一个对象的内存图**

![191014-21：06：29](.\image\191014-21：06：29.png)

**10 使用对象类型作为方法的参数**

- 当一个对象作为参数，传递到方法当中时，实际上传递进去的是对象的地址值。

**11 使用对象类型作为方法的返回值**

- 当使用一个对象类型作为方法的返回值时，返回值其实就是对象的地址值

**12 成员变量和局部变量的区别**

1. 定义的位置不一样【重点】
   
   局部变量：在方法的内部
   
   成员变量：在方法的外部，直接写在类中

2. 作用范围不一样【重点】
   
   局部变量：只有方法当中才可以使用，出了方法就不能再用
   
   成员变量：整个类全部可以通用

3. 默认值不一样【重点】
   
   局部变量：没有默认值，如果想要使用，必须手动进行赋值
   
   成员变量：如果没有赋值，会有默认值，规则跟数组一样

4. 内存的位置不一样（了解）
   
   局部变量：位于栈内存
   
   成员变量：位于堆内存

5. 生命周期不一样（了解）
   
   局部变量：随着方法进栈而诞生，随着方法出栈而消失
   
   成员变量：随着对象创建而诞生，随着对象被垃圾回收而消失

### **13 面向对象的三大特征之封装性**

1. 方法就是一种封装
2. 关键字private也是一种封装

封装就是将一些细节信息隐藏起来，对于外界不可见

**14 private关键字的作用及使用**

- 阻止不合理的数值被设置进来

- 对应要有Getter/Setter方法

- 提高代码的安全性

**15 练习使用private关键字定义学生类**

**16 this关键字的作用**

当方法的局部变量和类的成员变量重名的时候，根据“就近原则”，优先使用局部变量

如果需要访问本类当中的成员变量，需要使用格式：

this.成员变量名

通过谁调用的方法，谁就是this

### **17 构造方法**

1. 构造方法的名称必须和所有的类名称完全一样，就连大小写也要一样
2. 构造方法不要写返回值，连void都不写
3. 构造方法不能return一个具体的返回值
4. 如果没有编写任何构造方法，那么编译器会默认创建一个构造方法，没有参数、方法体什么也不做
5. 一旦编写了至少一个构造方法，那么编译器就不会自己构造
6. 构造方法也是可以重载的

**18 定义一个标准的类**

1. 所有的成员变量都要使用private关键字修饰
2. 为每一个成员变量编写一对Getter/Setter方法
3. 编写一个无参数的构造方法
4. 编写一个全参数的构造方法

# 三、常用API第一部分

## 3.1 Scanner类

**01 Api概述和使用步骤**

概述：API（Application ），应用程序编程接口

api文档：

​    看包路径

​    看构造方法，构造方法是new出来的东西

​    看方法摘要（成员方法）

**02 Scanner概述及其API文档的使用**

引用类型的一般使用步骤：

1. 导包
   
   import 包路径.类名称
   
   只有java.lang包下的内容不需要导包

2. 创建
   
   类名称 对象名 = new 类名称();

3. 使用
   
   对象名.成员方法名();

**03 Scanner的使用步骤**

Scanner.java

```
import java.util.Scanner;

public class Demo01Scanner {
    public static void main(String[] args) {
        // 创建
        Scanner sc = new Scanner(System.in);

        // 获取键盘输入的int数字
        int num = sc.nextInt();
        System.out.println(num);

        // 获取键盘输入的字符串
        String str = sc.next();
        System.out.println(str);
    }
}
```

**04 Scanner练习一：键盘输入两个数，求和**

```
        // 创建
        Scanner sc = new Scanner(System.in);

        System.out.println("请输入第一个数字：");
        // 获取键盘输入的int数字
        int num = sc.nextInt();

        System.out.println("请输入第二个数字：");
        // 获取键盘输入的字符串
        int num2 = sc.nextInt();

        int sum = num + num2;
        System.out.println("两个数相加和为："+sum);
```

**05 Scanne练习二：输入三个数字，输出最大值**

## 3.2 匿名对象

**01 匿名对象的说明**

匿名对象就是只有右边的对象，没有左边的名字和赋值运算符。

```
// 匿名对象
new Persion();
new Persion.name = "许三多";
```

- 注意事项：匿名对象只能使用唯一的一次，下次再用就要再创建一个新对象
- 使用建议：如果确定一个对象只需要用一次，就可以用

**02 匿名对象作为方法的参数和返回值**

## 3.3 Random类

**01 Random概述和基本使用**

生成随机数，random.nextInt();的范围是int的范围

```
        Random random = new Random();
        int i = random.nextInt();
        System.out.println("生成的随机数为" + i);
```

**02 Random生成指定范围的随机数**

[0,n)

```
   Random random = new Random();
   int i = random.nextInt(10); //0~9
   System.out.println("生成的随机数为：" + i);
```

**03 练习一：生成1-n**

生成0到n-1的随机数，再整体+1

**04 练习二：猜数字游戏**

## 3.4 ArrayList集合

**01 对象数组**

数组有一个缺点：一旦创建，程序运行期间长度不可以发生改变

**02 ArrayList集合概述和基本使用**

数组的长度不可以发生改变

但是ArrayList集合的长度是可以随意变化的

对于ArrayList来说，有一个尖括号<E>代表泛型

泛型：也就是装在集合当中的所有元素，全都是统一的什么类型

注意：泛型只能是引用类型，不能是基本类型

注意事项：

​    对于ArrayList来说，直接打印得到的不是地址值，而是内容

​    如果内容为空，得到的是空的中括号：[ ]

备注：1.7+开始，右侧的尖括号里面的类型可以省略不写

```
ArrayList<String> list = new ArrayList<>();
```

**03 ArrayList集合的常用方法和遍历**

- public boolean add(E e)：想集合当中添加元素，参数的类型和泛型一致
- public E get(int index)：：从集合获取元素，参数是索引编号，返回值时对应位置的元素。
- public E remove(int index)：从集合中删除元素，参数是索引编号，返回值就是被删除掉的元素。
- public int size()：获取集合的长度，返回值是集合中包含的元素个数。

**04 ArrayList集合存储基本数据类型**

如果希望向集合ArrayList当中存储基本数据类型，必须使用基本类型对应的"包装类"

| 基本类型    | 包装类           |
| ------- | ------------- |
| byte    | Byte          |
| short   | Short         |
| int     | **Integer**   |
| long    | Long          |
| fioat   | Float         |
| char    | **Character** |
| boolean | Boolean       |

**05 ArrayList练习一：随机存储数字**

生成6个1~33之间的随机整数，添加到集合，并遍历集合

```
ArrayList<Integer> list = new ArrayList<>();
    Random r = new Random();
    for (int i = 0; i < 6; i++) {
        int num = r.nextInt(32)+1;
        list.add(num);
    }
    for (int i = 0; i < list.size(); i++) {
        System.out.println(list.get(i));
    }
```

**06 ArrayList练习二：存储自定义类型**

**07 ArrayList练习四：筛选集合中的随机数**

main方法

```
        ArrayList<Integer> bigList = new ArrayList<>();

        Random random = new Random();
        for (int i = 0; i < 20; i++) {
            int num = random.nextInt(100)+1;
            bigList.add(num);
        }
        for (int i = 0; i < bigList.size(); i++) {
            System.out.println(bigList.get(i));
        }
        System.out.println("=================");
        ArrayList<Integer> smollList  = inputArray(bigList);
        for (int i = 0; i < smollList.size(); i++) {
            System.out.println(smollList.get(i));
        }
```

自定义的方法

```
    public static ArrayList<Integer> inputArray(ArrayList<Integer> bigList){
        ArrayList<Integer> smollList = new ArrayList<>();

        for (int i = 0; i < bigList.size(); i++) {
            if (bigList.get(i)%2==0){
                smollList.add(bigList.get(i));
            }
        }
        return smollList;
    };
```

## 3.5 String类

**01 字符串概述和特点**

java.lang.String类代表字符串

API中说：Java程序中的所有字符串字面量（如”abc“）走作为此类的实例类型

其实就是说：程序当中所有的双引号字符串，都是String类的对象。（就算没有new，也照样是。）

特点：

1. 字符串的内容用不改变【重点】
2. 字符串可以共享
3. 字符串相当于char[]字符数组，但是底层原理是byte[ ]字节数组

**02 字符串的构造方法和直接创建**

常见的三种构造方法：

1. public String( )：创建一个空白字符串，不含任何内容

2. public String(char[] arrat)：根据字符数组的内容，来创建对应的字符串

3. public String(byte[] array)：根据字节数组的内容，来创建对应的字符串
   
   ```
   String a = new String();
   
   char[] chara = {'2','d','s','8'};
   String stra = new String(chara);
   System.out.println(stra);
   
   byte[] bytes = {97,98,33,64,56};
   String strb = new String(bytes);
   System.out.println(strb);
   ```

**03 字符串的常量池（位于堆当中）**

字符串常量池：程序当中直接写上的双引号字符串，就在字符串常量池中

![191016-20：28：27](.\image\191016-20：28：27.png)

**04 字符串的比较相关方法**

== 是进行对象的地址值比较，如果确实需要字符串的内容比较，可以使用两个方法：

public boolean aquals(Object obj)：参数可以是任何对象，只有参数是一个字符串并且内容相同的才会返回true，否则返回false

注意事项：

1. 任何对象都能用Object进行接收

2. equals方法具有对称性，也就是a.equals(b)和b.equals(a)效果一样

3. 如果比较双方一个常量一个变量，推荐把常量字符串写在前面。
   
   推荐L：“abc”.equals(str)  不推荐：str.equals("abc")，因为有可能会报空指针异常

public boolean equalsIgnoreCase(String str)：忽略大小写，进行内容比较

**05 字符串的获取相关方法**

常用方法：

public int length()：获取字符串当中含有的字符个数，拿到字符串长度

public String concat(String str)：将当前字符串和参数字符串拼接成为新的字符串，返回值为新的字符串

public char charAt(int index)：获取指定索引位置的单个字符。（索引从0开始）

public int indexOf(String str)：查找参数字符串在本字符串当中首次出现的索引位置，如果没有则返回-1

**06 字符串的截取方法**

public String substring(int index)：截取从参数位置一直到字符串末尾，返回新字符串

public String substring(int begin, int end)：截取从begin开始，一直到end结束，中间的字符串

备注：[begin, end)，包含左边，不包含右边

**07 字符串的转换相关方法**

public char[ ] toCharArray()：将当前字符串拆分成为字符数组作为返回值

public byte[ ] getByte()：获取当前字符串底层的字节数组

public String replace(CharSequence oldString, CharSequence newString)：将所有出现的老字符串替换成为新的字符串，返回替换之后的结果新字符串。

**08 字符串的分割方法**

public String[ ] split(String regex)：按照参数的规则，将字符串切分成为若干部分

注意：

​    split方法的参数其实是一个“正则表达式”

​    如果按照"."进行划分，必须写成"\ \ ."

**09 练习：按指定格式拼接字符串**

**10 练习：统计输入的字符串各种字符的个数**

## 3.6 static静态

**01 静态static关键字概述**

一旦使用了static关键字，那么这样的内容不再属于对象自己，而是属于类的，所以凡是本类的对象，都共享同一份



**02 静态static关键字修饰成员变量**

- 如果一个成员变量使用了static关键字，那么这个变量不再属于对象自己，而是属于所在的类。多个对象共享一份数据



**03 静态static关键字修饰成员方法**（看到这）

- 一旦使用了static修饰成员方法，那么这就成为了静态方法。静态方法不属于对象，而是属于类的。
- 如果没有static关键字，那么必须首先创建对象，然后通过对象才能使用它。

类名称.静态方法

**04 静态static的内存图**

**05 静态代码块**

## 3.7 Arrays工具类

## 3.8 Math类

