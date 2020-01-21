- Java是基于JVM虚拟机的跨平台语言，一次编写，到处运行；
- Java程序易于编写，而且有内置垃圾收集，不必考虑内存管理；
- Java虚拟机拥有工业级的稳定性和高度优化的性能，且经过了长时期的考验；
- Java拥有最广泛的开源社区支持，各种高质量组件随时可用。

# 1 Java简介
Java介于编译型语言和解释型语言之间。Java是将代码编译成一种“字节码”，它类似于抽象的CPU指令，然后，针对不同平台编写虚拟机，不同平台的虚拟机负责加载字节码并执行，这样就实现了“一次编写，到处运行”的效果。

随着Java的发展，SUN给Java又分出了三个不同版本：
- Java SE：Standard Edition
- Java EE：Enterprise Edition
- Java ME：Micro Edition

简单来说，Java SE就是标准版，包含标准的JVM和标准库，而Java EE是企业版，它只是在Java SE的基础上加上了大量的API和库，以便方便开发Web应用、数据库、消息服务等，Java EE的应用使用的虚拟机和Java SE完全相同。

Java ME就和Java SE不同，它是一个针对嵌入式设备的“瘦身版”，Java SE的标准库无法在Java ME上使用，Java ME的虚拟机也是“瘦身版”。

因此我们推荐的Java学习路线图如下：

1.首先要学习Java SE，掌握Java语言本身、Java核心开发技术以及Java标准库的使用；

2.如果继续学习Java EE，那么Spring框架、数据库开发、分布式架构就是需要学习的；

3.如果要学习大数据开发，那么Hadoop、Spark、Flink这些大数据平台就是需要学习的，他们都基于Java或Scala开发；

4.如果想要学习移动开发，那么就深入Android平台，掌握Android App开发。

### 名词解释
- JDK：Java Development Kit
- JRE：Java Runtime Environment

简单地说，JRE就是运行Java字节码的虚拟机。但是，如果只有Java源码，要编译成Java字节码，就需要JDK，因为JDK除了包含JRE，还提供了编译器、调试器等开发工具。

- JSR规范：Java Specification Request
- JCP组织：Java Community Process

## 1-1 安装JDK
Download : https://www.oracle.com/technetwork/java/javase/downloads/jdk13-downloads-5672538.html

- java：这个可执行程序其实就是JVM，运行Java程序，就是启动JVM，然后让JVM执行指定的编译后的代码；
- javac：这是Java的编译器，它用于把Java源码文件（以.java后缀结尾）编译为Java字节码文件（以.class后缀结尾）；
- jar：用于把一组.class文件打包成一个.jar文件，便于发布；
- javadoc：用于从Java源码中自动提取注释并生成文档；
- jdb：Java调试器，用于开发阶段的运行调试。

## 1-2 第一个Java程序
```
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

- 一个Java源码只能定义一个public类型的class，并且class名称和文件名要完全一致；
- 使用javac可以将.java源码编译成.class字节码；
- 使用java可以运行一个已编译的Java程序，参数是类名。

## 1-3 Java代码助手
## 1-4 IDE
IDE是集成开发环境：Integrated Development Environment的缩写。

- Eclipse (https://www.eclipse.org/downloads/packages/)
- IntelliJ Idea
- NetBeans

## 1-5 IDE练习插件

# 2 Java程序基础
## 2-1 基本结构
```
/**
 * 可以用来自动创建文档的注释
 */
public class Hello { // 类名是Hello
    public static void main(String[] args) {
        // 向屏幕输出文本:
        System.out.println("Hello, world!");
        /* 多行注释开始
        注释内容
        注释结束 */
    }
} // class定义结束
```
类名要求：
- 类名必须以英文字母开头，后接字母，数字和下划线的组合
- 习惯以大写字母开头

注意到public是访问修饰符，表示该class是公开的。不写public，也能正确编译，但是这个类将无法从命令行执行。

void : 没有任何返回值

Java入口程序规定的方法必须是静态方法，方法名必须为main，括号内的参数必须是String数组。

方法名也有命名规则，命名和class一样，但是首字母小写

注释：
- 单行：//
- 多行：/* ... */
- 特殊多行：/\*\*...*/ (这种特殊的多行注释需要写在类和方法的定义处，可以用于自动创建文档。)

快速格式化代码：Ctrl+Shift+F

## 2-2 变量和数据类型
在Java中，变量分为两种：基本类型的变量和引用类型的变量。

在Java中，变量必须先定义后使用，在定义变量的时候，可以给它一个初始值。不写初始值，就相当于给它指定了默认值。默认值总是0。

```
public class Main {
    public static void main(String[] args) {
        int x = 100; // 定义int类型变量x，并赋予初始值100
        System.out.println(x); // 打印该变量的值
    }
}
```

### 基本数据类型
基本数据类型是CPU可以直接进行运算的类型。Java定义了以下几种基本数据类型：
- 整数类型：byte（1字节），short（2字节），int（4字节），long（8字节）
- 浮点数类型：float（4字节），double（8字节）
- 字符类型：char（2字节）
- 布尔类型：boolean

1字节（byte）= 8比特（bit），表示范围0-255

### 整型
对于整型类型，Java只定义了带符号的整型，因此，最高位的bit表示符号位（0表示正数，1表示负数）。各种整型能表示的最大范围如下：
- byte：-128 ~ 127
- short: -32768 ~ 32767
- int: -2147483648 ~ 2147483647
- long: -9223372036854775808 ~ 9223372036854775807

### 浮点型
对于float类型，需要加上f后缀。
浮点数可表示的范围非常大，float类型可最大表示3.4x10^38，而double类型可最大表示1.79x10^308。

### 布尔类型
```
boolean b1 = true;
boolean b2 = false;
boolean isGreater = 5 > 3; // 计算结果为true
int age = 12;
boolean isAdult = age >= 18; // 计算结果为false
```

### 字符类型
```
public class Main {
    public static void main(String[] args) {
        char a = 'A';
        char zh = '中';
        System.out.println(a);
        System.out.println(zh);
    }
}
```

注意char类型使用单引号'，且仅有一个字符，要和双引号"的字符串类型区分开。

### 常量
定义变量的时候，如果加上final修饰符，这个变量就变成了常量。常量在定义时进行初始化后就不可再次赋值，再次赋值会导致编译错误。

根据习惯，常量名通常全部大写。

### var关键字
有些时候，类型的名字太长，写起来比较麻烦。这个时候，如果想省略变量类型，可以使用var关键字：
```
var sb = new StringBuilder(); //等价于StringBuilder sb = new StringBuilder();
```

### 变量的作用范围
在Java中，多行语句用{ }括起来。很多控制语句，例如条件判断和循环，都以{ }作为它们自身的范围，只要正确地嵌套这些{ }，编译器就能识别出语句块的开始和结束。

## 2-3 整数运算
整数的数值表示不但是精确的，而且整数运算永远是精确的，即使是除法也是精确的，因为两个整数相除只能得到结果的整数部分。求余运算使用%。

特别注意：整数的除法对于除数为0时运行时将报错，但编译不会报错。

### 溢出
```
public class Main {
    public static void main(String[] args) {
        int x = 2147483640;
        int y = 15;
        int sum = x + y;
        System.out.println(sum); // -2147483641
    }
}
```
要解决上面的问题，可以把int换成long类型，由于long可表示的整型范围更大，所以结果就不会溢出。

### 移位运算
可以对整数进行移位运算。对整数7左移1位将得到整数14，左移两位将得到整数28。
```
int n = 7;       // 00000000 00000000 00000000 00000111 = 7
int a = n >> 1;  // 00000000 00000000 00000000 00000011 = 3
```
如果对一个负数进行右移，最高位的1不动，结果仍然是一个负数。
```
int n = -536870912;
int a = n >> 1;  // 11110000 00000000 00000000 00000000 = -268435456
```
还有一种不带符号的右移运算，使用>>>，它的特点是符号位跟着动，因此，对一个负数进行>>>右移，它会变成正数，原因是最高位的1变成了0。

对byte和short类型进行移位时，会首先转换为int再进行位移。

仔细观察可发现，左移实际上就是不断地×2，右移实际上就是不断地÷2。

### 位运算
- 与运算的规则是，必须两个数同时为1，结果才为1
- 或运算的规则是，只要任意一个为1，结果就为1
- 非运算的规则是，0和1互换
- 异或运算的规则是，如果两个数不同，结果为1，否则为0

对两个整数进行位运算，实际上就是按位对齐，然后依次对每一位进行运算。

### 运算优先级
在Java的计算表达式中，运算优先级从高到低依次是：
- ()
- ! ~ ++ --
- \* / %
- \+ \-
- << >> >>>
- &
- |
- += -= *= /=

### 类型自动提升与强制转型
在运算过程中，如果参与运算的两个数类型不一致，那么计算结果为较大类型的整型。例如，short和int计算，结果总是int，原因是short首先自动被转型为int。

也可以将结果强制转型，即将大范围的整数转型为小范围的整数。强制转型使用(类型)，例如，将int强制转型为short。要注意，超出范围的强制转型会得到错误的结果，原因是转型时，int的两个高位字节直接被扔掉，仅保留了低位的两个字节

## 2-4 浮点数运算
浮点数运算和整数运算相比，只能进行加减乘除这些数值计算，不能做位运算和移位运算。

在计算机中，浮点数虽然表示的范围大，但是，浮点数有个非常重要的特点，就是浮点数常常无法精确表示。

由于浮点数存在运算误差，所以比较两个浮点数是否相等常常会出现错误的结果。正确的比较方法是判断两个浮点数之差的绝对值是否小于一个很小的数

如果参与运算的两个数其中一个是整型，那么整型可以自动提升到浮点型。

### 溢出
整数运算在除数为0时会报错，而浮点数运算在除数为0时，不会报错，但会返回几个特殊值：
- NaN表示Not a Number
- Infinity表示无穷大
- -Infinity表示负无穷大

### 强制转型
可以将浮点数强制转型为整数。在转型时，浮点数的小数部分会被丢掉。如果转型后超过了整型能表示的最大范围，将返回整型的最大值。如果要进行四舍五入，可以对浮点数加上0.5再强制转型。

## 2-5 布尔运算
### 短路运算
布尔运算的一个重要特点是短路运算。如果一个布尔运算的表达式能提前确定结果，则后续的计算不再执行，直接返回结果。

### 三元运算符
b ? x : y

## 2-6 字符和字符串
### 字符类型
字符类型char是基本数据类型，它是character的缩写。一个char保存一个Unicode字符。

要显示一个字符的Unicode编码，只需将char类型直接赋值给int类型即可：
```
int n1 = 'A'; // 字母“A”的Unicodde编码是65
```
还可以直接用转义字符\u+Unicode编码来表示一个字符：
```
char c4 = '\u4e2d'; // '中'，因为十六进制4e2d = 十进制20013
```

### 字符串类型
和char类型不同，字符串类型String是引用类型，我们用双引号"..."表示字符串。一个字符串可以存储0个到任意个字符。
```
String s = "abc\"xyz"; // 包含7个字符: a, b, c, ", x, y, z
```

### 多行字符串
从Java 13开始，字符串可以用"""..."""表示多行字符串（Text Blocks）了：
```
String s = """ 
           SELECT * FROM
             users
           WHERE id > 100
           ORDER BY name DESC""";
```
最后，由于多行字符串是作为Java 13的预览特性（Preview Language Features）实现的，编译的时候，我们还需要给编译器加上参数：
```
javac --source 13 --enable-preview Main.java
```

### 不可变特性
Java的字符串除了是一个引用类型外，还有个重要特点，就是字符串不可变。

### 空值null
引用类型的变量可以指向一个空值null，它表示不存在，即该变量不指向任何对象。

## 2-7 数组类型
定义一个数组类型的变量，使用数组类型“类型[]”，例如，int[]。和单个基本类型变量不同，数组变量初始化必须使用new int[5]表示创建一个可容纳5个int元素的数组。

Java的数组有几个特点：
- 数组所有元素初始化为默认值，整型都是0，浮点型是0.0，布尔型是false；
- 数组一旦创建后，大小就不可改变。

可以修改数组中的某一个元素，使用赋值语句，例如，ns[1] = 79;。

可以用数组变量.length获取数组大小：
```
System.out.println(ns.length);
```
也可以在定义数组时直接指定初始化的元素，这样就不必写出数组大小，而是由编译器自动推算数组大小。例如：
```
int[] ns = { 68, 79, 91, 85, 62 };
```

### 字符串数组
如果数组元素不是基本类型，而是一个引用类型，那么，
```
names[1] = "cat";
```
仅仅是将names[1]的引用从指向"XYZ"改成了指向"cat"，其结果是字符串"XYZ"再也无法通过names[1]访问到了。

# 3 流程控制
## 3-1 输入和输出

### 输出
```
System.out.println();
System.out.print()
```

### 格式化输出
```
System.out.printf("%.2f\n", d);
System.out.printf("n=%d, hex=%08x", n, n); // 注意，两个%占位符必须传入两个数
```
详细的格式化参数请参考JDK文档java.util.Formatter

### 输入
```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // 创建Scanner对象
        System.out.print("Input your name: "); // 打印提示
        String name = scanner.nextLine(); // 读取一行输入并获取字符串
        System.out.print("Input your age: "); // 打印提示
        int age = scanner.nextInt(); // 读取一行输入并获取整数
        System.out.printf("Hi, %s, you are %d\n", name, age); // 格式化输出
    }
}
```
System.out代表标准输出流，而System.in代表标准输入流。直接使用System.in读取用户输入虽然是可以的，但需要更复杂的代码，而通过Scanner就可以简化后续的代码。

有了Scanner对象后，要读取用户输入的字符串，使用scanner.nextLine()，要读取用户输入的整数，使用scanner.nextInt()。Scanner会自动转换数据类型，因此不必手动转换。要测试输入，我们不能在线运行它，因为输入必须从命令行读取，因此，需要走编译、执行的流程。

## 3-2 if判断
```
public class Main {
    public static void main(String[] args) {
        int n = 70;
        if (n >= 90) {
            System.out.println("优秀");
        } else if (n >= 60) {
            System.out.println("及格了");
        } else {
            System.out.println("挂科了");
        }
        System.out.println("END");
    }
}
```

### 判断值相等
利用差值小于某个临界值来判断。

### 判断是否指向同一对象
==

### 判断引用内容相等
equals()

### 3-3 switch多重选择

# 4 数组操作
