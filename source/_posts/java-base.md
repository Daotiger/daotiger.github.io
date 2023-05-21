---
title: Java基础
---

# 参考官方文档

[The Java™ Tutorials](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/index.html)


## 关键字

参考官方文档[Java Language Keywords](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html)

||||||
|:---|:---|:---:|---:|---:|
|abstract | continue | for | new |switch
|assert[^***] | default | goto[^*] | package | synchronized
|boolean	|do	|if	|private	|this
|break|double|implements|protected|throw
|byte|else|import|public|throws
|case|enum[^****]	|instanceof|return|transient
|catch|extends|int|shortshort|try
|char|final|interface|static|void
|class|finally|long|strictfp[^**]|volatile
|const[^*]|float|native|super|while

[^*]    not used

[^**] 	added in 1.2

[^***]	added in 1.4

[^****] added in 5.0

## 标识符


标识符,即开发者自己定义的类/方法变量等名称

### 变量

Java 编程语言定义了以下类型的变量：

- 实例变量（非静态字段）从技术上讲，对象将其各个状态存储在“非静态字段”中，即声明的字段没有关键字。非静态字段也称为实例变量，因为它们的值对于类的每个实例（换句话说，对于每个对象）都是唯一的;一辆自行车独立于另一辆自行车。
  
    static currentSpeed
  
- 类变量（静态字段）类变量是用修饰符声明的任何字段;这告诉编译器，无论该类已实例化多少次，都存在此变量的一个副本。定义特定类型自行车的齿轮数的字段可以标记为，因为从概念上讲，相同数量的齿轮将适用于所有实例。代码将创建这样的静态字段。此外，可以添加关键字以指示齿轮数量永远不会改变。
  
    final static int numGears = 6;
  
- 局部变量与对象在字段中存储其状态的方式类似，方法通常会将其临时状态存储在局部变量中。声明局部变量的语法类似于声明字段（例如，）。没有将变量指定为局部变量的特殊关键字;该决定完全来自声明变量的位置 - 即方法的左大括号和右大括号之间。因此，局部变量仅对声明它们的方法可见;他们无法从班级的其他成员访问。
  
    int count = 0;

- 参数您已经在类和“Hello World！”应用程序的方法中看到了参数示例。回想一下，该方法的签名是 。在这里，变量是此方法的参数。要记住的重要一点是，参数始终被归类为“变量”而不是“字段”。这也适用于其他参数接受构造（例如构造函数和异常处理程序），您将在本教程后面了解这些构造。
  
    public static void main(String[] args)args


### 命名

每种编程语言对于允许您使用的名称类型都有自己的一套规则和约定，Java 编程语言也不例外。命名变量的规则和约定可以总结如下：

- 变量名称区分大小写。变量的名称可以是任何合法标识符 — 无限长度的 Unicode 字母和数字序列，以字母、美元符号 “” 或下划线字符 “” 开头。但是，约定是始终以字母开头变量名称，而不是 “” 或 “”。此外，按照惯例，根本不使用美元符号字符。您可能会发现在某些情况下，自动生成的名称将包含美元符号，但您的变量名称应始终避免使用它。下划线字符也存在类似的约定;虽然从技术上讲，以 “” 开头的变量名称是合法的，但不鼓励这种做法。不允许使用空格。$_$__

- 后续字符可以是字母、数字、美元符号或下划线字符。惯例（和常识）也适用于此规则。为变量选择名称时，请使用完整的单词，而不是隐晦的缩写。这样做将使代码更易于阅读和理解。在许多情况下，它还会使您的代码自我记录;例如，名为 、 和 的字段比缩写版本（如 、 和 ）直观得多。另请记住，您选择的名称不得是关键字或保留字。cadencespeedgearscg

- 如果您选择的名称仅包含一个单词，请用所有小写字母拼写该单词。如果它由多个单词组成，请将每个后续单词的首字母大写。这些名称和是该公约的主要例子。如果变量存储常量值（如 ），则约定略有变化，将每个字母大写，并用下划线字符分隔后续单词。按照惯例，下划线字符永远不会在其他地方使用。
  
    static final int NUM_GEARS = 6


## 基础数据类型

- byte 字节,数据类型为 8 位有符号二进制的补码整数。它的最小值为 -128，最大值为 127（含）。

- short 短整型,数据类型是 16 位有符号二进制的补码整数。它的最小值为 -32768，最大值为 32767（含）。

- int 整型, 默认情况下，数据类型为 32 位有符号二进制补码整数，最小值为 -2 <sup>31</sup>，最大值为 2<sup>31</sup>-1

- long 长整型,数据类型为 64 位二进制补码整数。带符号长整型的最小值为 -2 <sup>63</sup>，最大值为 2<sup>63</sup>-1

    在 Java SE 8 及更高版本中，可以使用数据类型来表示无符号的 64 位长整型，该长整型的最小值为 0，最大值为 2<sup>64</sup>-1

- float 单精度浮点数,数据类型为单精度 32 位 IEEE 754 浮点数。

- double 双精度浮点数, 数据类型为双精度 64 位 IEEE 754 浮点数。

- boolean 布尔类型, true / false

- char 字符, 数据类型是单个 16 位 Unicode 字符。它的最小值为 （或 0），最大值为(65535).char'\u0000''\uffff'



### 默认值

|数据类型|默认值|
|:---|:---|
| byte | 0 |
| short | 0 |
| int | 0 |
| long | 0L |
| float | 	0.0f |
| double | 	0.0d |
| char | '\u0000' |
| String(或对象)  | null |
| boolean | false |



## 数组

数组是一个容器对象，它保存单个类型的固定数量的值。数组的长度是在创建数组时确定的。创建后，其长度是固定的。



### 声明变量以引用数组


前面的程序使用以下代码行声明一个数组（名为 ）：anArray

```java
// 声明一个整数数组
int[] anArray;
```

数组声明有两个组成部分：数组的**类型**和数组的**名称**。

同样，您可以声明其他类型的数组：

```java
byte[] anArrayOfBytes;
short[] anArrayOfShorts;
long[] anArrayOfLongs;
float[] anArrayOfFloats;
double[] anArrayOfDoubles;
boolean[] anArrayOfBooleans;
char[] anArrayOfChars;
String[] anArrayOfStrings;
```

您还可以在数组名称后放置括号：

```java
// 不鼓励使用这种形式
float anArrayOfFloats[];
```

### 创建、初始化和访问数组

```java
// 创建一个大小为10的数组 , 不初始化必须指定大小. 动态初始化.
int[] anArray = new int[10];

// 创建并初始化数据 , 不指定大小,必须初始化. 静态初始化.
int[] anArray = []{ 
    100, 200, 300,
    400, 500, 600, 
    700, 800, 900, 1000
};
//静态初始化 简写方式.
int[] anArray = {1,2,3};
```

### 数组的操作

数组是的属性长度length


```java

//遍历
 for(int i= 0, length = anArray.length; i < length; i++ ){
    System.out.println(anArray[i]);
}

for(int i : anArray){
    System.out.println(anArray[i]);
}
```

#### 数组工具类

```
java.util.Arrays Arrays
```
- 在数组中搜索特定值以获取该值所在的索引 放置（方法）。binarySearch

- 比较两个数组以确定它们是否相等（方法）。equals

- 填充数组以在每个索引（方法）处放置特定值。fill

- 按升序对数组进行排序。这可以完成 按顺序使用该方法，或同时使用 Java SE 8 中引入的方法。并行排序 多处理器系统上的大型阵列比顺序阵列排序更快。sortparallelSort

- 创建使用数组作为其源的流（方法）。streamcopyTo



### 多维数组

二维数组也叫矩阵

二位数组的格式 

```java
int [] []  arr = new int [m][n];
```









