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

# 1-2 安装JDK
Download : https://www.oracle.com/technetwork/java/javase/downloads/jdk13-downloads-5672538.html

- java：这个可执行程序其实就是JVM，运行Java程序，就是启动JVM，然后让JVM执行指定的编译后的代码；
- javac：这是Java的编译器，它用于把Java源码文件（以.java后缀结尾）编译为Java字节码文件（以.class后缀结尾）；
- jar：用于把一组.class文件打包成一个.jar文件，便于发布；
- javadoc：用于从Java源码中自动提取注释并生成文档；
- jdb：Java调试器，用于开发阶段的运行调试。

# 1-3 第一个Java程序
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

# 2 Java程序基础


# 3 流程控制

# 4 数组操作
