
## 一.String
* 字符串一旦被赋值，内容不能改变(不是引用不能改变)
	例如：String s = “hello”;
	也就是说,在字符串常量池中，地址0x001对应”hello”，该地址值对应的字符串不能改变。
	如果要将helloworld赋值给s，则要将s指向”helloworld”的地址0x002。


* 字面值作为字符串对象和通过构造方法创建对象的不同
	String s = new String("hello");和String s = "hello"的区别?
	第一条语句创建了两个对象，在常量池中创建了”hello”，在堆中创建了”new String()”
	引用s先指向”new String()”，再由new String指向”hello”
	第二条语句创建了一个对象，在常量池中创建了”hello”。用用s直接指向”hello”

* String，StringBuffer和StringBuilder的区别？
1)String内容不可变，后面两个内容可变。
2)StringBuffer是同步的，数据安全，效率低（有些方法被synchronized修饰了，适用于多线程）
3)StringBuilder是不同步的，数据不安全，效率高（适用于单线程），该类用的最多。

* StringBuffer和String类型做形参，参数传递问题对比测试

```java
public static void main(String[] args) {
   Student s1 = new Student("林",27);
   Student s2 = new Student("刘",30);
   change1(s1,s2);
   System.out.println("s1:"+s1.getAge()+"---"+s1.getName());
   System.out.println("s2:"+s2.getAge()+"---"+s2.getName());
   System.out.println("--------change1方法和change2方法对比--------");
   Student s3 = new Student("王",35);
   Student s4 = new Student("张",32);
   change2(s3,s4);
   System.out.println("s3:"+s3.getAge()+"---"+s3.getName());
   System.out.println("s4:"+s4.getAge()+"---"+s4.getName());
}

private static void change2(Student s3, Student s4) {
	s3.setAge(100);//对s3的地址值的内容赋值
	s3.setName("赵");//对s3的地址值的内容赋值
}

private static void change1(Student s1, Student s2) {
	s1 = s2;//把s2的地址值给s1，也就是说s1和s2都指向s2原来的地址值
	s1.setAge(100);//对s2原来的地址值的内容赋值
	s1.setName("赵");//对s2原来的地址值的内容赋值	
}
```

## 二.Integer
* Integer i = 1; i += 1;做了哪些事情

```java
	Integer i = Integer.valueOf(3);//自动装箱
	Integer a = new Integer(3);
	Integer b = 3;                  // 将3自动装箱成Integer类型
	int c = 3;
	System.out.println(a == b);     // false 两个引用没有引用同一对象
	System.out.println(a == c);     // true a自动拆箱成int
	System.out.println(b == c);     // true a自动拆箱成int
	System.out.println(i == a);     // false
	System.out.println(i == b);     // true
	System.out.println(i == c);     // true 
	
	
	Integer f1 = 100, f2 = 100, f3 = 150, f4 = 150;

	//如果整型字面量的值在-128到127之间，那么不会new新的Integer对象，而是直接引用常量池中的Integer对象，
	//所以f1==f2的结果是true，而f3==f4的结果是false。
	System.out.println(f1 == f2);   //true
	System.out.println(f3 == f4);   //false
```

## 三.Short
* short s1 = 1; s1 = s1 + 1;有错吗?short s1 = 1; s1 += 1;有错吗？
	对于short s1 = 1; s1 = s1 + 1;由于1是int类型，因此s1+1运算结果也是int 型，需要强制转换类型才能赋值给short型。
	而short s1 = 1; s1 += 1;可以正确编译，因为s1+= 1;相当于s1 = (short)(s1 + 1);其中有隐含的强制类型转换。
	
## 四.Math
* Math.round(11.5) 等于多少？Math.round(-11.5)等于多少？
	Math.round(11.5)的返回值是12，Math.round(-11.5)的返回值是-11。
	四舍五入的原理是在参数上加0.5然后进行下取整。



