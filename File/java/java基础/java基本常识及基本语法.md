
## 一.基本概念及理念
* java设计原则及语言特点
设计原则：对扩展开放，对修改关闭
语言特点：开源、跨平台

* 项目设计理念
分析是从具体到抽象，实现是从抽象到具体（先定义接口，再定义抽象类，最后定义实现子类）

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

![java编译执行过程](https://github.com/zhyzhy5/BigData/blob/master/java/java%E5%9F%BA%E7%A1%80/images/java%E7%BC%96%E8%AF%91%E6%89%A7%E8%A1%8C%E8%BF%87%E7%A8%8B.jpg "java编译执行过程")


## 二.关键字及标识符的特点
* 关键字总结
	1)Instanceof：判断该示例是否属于这个类
```java
Student s = new Student();
System.out .println(s instanceof Student);//判断s是否是Student类的示例:true
```
	2)transient：临时的
	在单线继承关系的类图中，被修饰的成员变量不能被序列化
	
	3)final：最终的
	3.1)修饰类，类不能被继承
	3.2)修饰变量:
		基本类型：基本类型的值不能改变 
		引用类型：引用类型的地址值不能改变。不能重新
		final Student s = new Student();
		s = new Student();//是错误的，因为重新为S分配了地址空间
	3.3)修饰方法，方法不能被重写


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

* 权限修饰符

|   | public | protected | default | private |
| :---- | :---- | :---- | :---- | :---- |
| 同一类中 | ok | ok | ok | ok |
| 同一包中 | ok | ok | ok |  |
|  | ok | ok |  |  |
| 不同包 | ok |  |  |  ||


## 三.原码，反码，补码
* 基本概念
	反码：正数的反码与其原码相同；负数的反码是对其原码逐位取反，但符号位除外。
	补码：正数的补码与其原码相同；负数的补码是在其对应正数的反码的末位加1。
	所有数据的运算都是采用补码进行的。
	
## 四.数据类型分类及转换
![数据类型分类及转换](https://github.com/zhyzhy5/BigData/blob/master/java/java%E5%9F%BA%E7%A1%80/images/%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%88%86%E7%B1%BB%E5%8F%8A%E8%BD%AC%E6%8D%A2.jpg "数据类型分类及转换")

| 基本数据类型 | Byte | Short | Int | Long | Boolean | Char | Float | Double |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 占字节空间 | 1 | 2 | 4 | 8 | 1 | 2 | 4 | 8 |

* 数据类型之间的转换
	1)byte,short,char—>int—>long—>float—>double
	2)byte,short,char相互之间补转换，他们参与运算首先转换为int类型

* 两个原则
	1)谁和字符串拼接，结果都是字符串类型
	2)char和int做"+"，结果为整数

## 五.系统的内存空间类型
	1)栈:很小，操作起来最快。存储局部变量，数据使用完毕，就消失
	
	2)堆:存储new出来的东西
	2.1)每一个实体(new出来的东西)都有首地址值
	2.2)每一个实体内的数据(变量)都有默认值
		byte,short,int,long 0
		float,double 0.0
		char ‘\u0000’
		boolean false
		引用类型：null
	2.3)使用完毕后，会被垃圾回收器空闲的时候回收。

	3)方法区:字符串常量池，基本类型
	4)本地方法区
	5)寄存器
	
## 六.数组
* 初始化方式

```
int[] a = new int[3];//动态初始化
Int[] b = {1,2,3};//静态初始化
int[] x,y[];//这种定义x是一个一维数组。y是一个二维数组。
```
	

	
