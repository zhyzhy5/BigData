
## 一.基本概念及理念
* java设计原则及语言特点
设计原则：对扩展开放，对修改关闭
语言特点：开源、跨平台

* 一个类的结构
	成员变量：是这个类的属性

	构造方法：
	1)用来创建对象
	2)给成员变量赋值

	成员方法：
	1)有构造方法，就创建对象；没有构造方法，成员可能都是静态的，直接通过类名调用

* jvm、jre、jkd间的关系
	1)JVM是JAVA虚拟机，保证跨平台
	2)JRE是JAVA运行环境，包括JVM和JAVA核心类库
	3)JDK是JAVA开发环境，包括JRE和开发工具，其中的开发工具：编译工具(javac.exe)打包工具(jar.exe)等
	使用JDK开发完成的java程序，交给JRE去运行。其中javac就是java compile

* java编译执行过程
	1)编写java文件
	2)通过Javac生成”.class”文件
	3)通过Java命令执行.class文件

！[java编译执行过程](http://static.runoob.com/images/runoob-logo.png "java编译执行过程")


## 二.关键字及标识符的特点
* 关键字总结
	1)Instanceof：判断该示例是否属于这个类
```java
Student s = new Student();
System.out .println(s instanceof Student);//判断s是否是Student类的示例:true
```
	2)transient：临时的
	在单线继承关系的类图中，被修饰的成员变量不能被序列化

* 标识符总结
	1)包：全部小写，如：liuyi,cn.itcast
	2)类或者接口：每个单词首字母大写，如：Student
	3)方法和变量：第一个单词首字母小写，从第二个单词开始，每个单词首字母大写，如：name,main,studentName（注意：构造方法除外，因为构造方法名和类名一样，第一个字母要大写）
	4)常量：全部大写，如：MAX,STUDENT_MAX_AGE
	常量分为两种：
	4.1)字面值常量：10，true，”hello”
	4.2)自定义常量：
```java
final int x = 100; 
final Student s = newStudent();//地址值不能变了，不能再new了
```

## 三.原码，反码，补码
* 基本概念
	反码：正数的反码与其原码相同；负数的反码是对其原码逐位取反，但符号位除外。
	补码：正数的补码与其原码相同；负数的补码是在其对应正数的反码的末位加1。
	所有数据的运算都是采用补码进行的。
	
## 四.数据类型分类及转换
![数据类型分类及转换](http://static.runoob.com/images/runoob-logo.png "数据类型分类及转换")

| 基本数据类型 | Byte | Short | Int | Long | Boolean | Char | Float | Double |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 占字节空间 | 1 | 2 | 4 | 8 | 1 | 2 | 4 | 8 |

* 数据类型之间的转换
	1)byte,short,char—>int—>long—>float—>double
	2)byte,short,char相互之间补转换，他们参与运算首先转换为int类型

* 两个原则
	1)谁和字符串拼接，结果都是字符串类型
	2)char和int做“+”，结果为整数

	
