
## һ.String
* �ַ���һ������ֵ�����ݲ��ܸı�(�������ò��ܸı�)
	���磺String s = ��hello��;
	Ҳ����˵,���ַ����������У���ַ0x001��Ӧ��hello�����õ�ֵַ��Ӧ���ַ������ܸı䡣
	���Ҫ��helloworld��ֵ��s����Ҫ��sָ��helloworld���ĵ�ַ0x002��


* ����ֵ��Ϊ�ַ��������ͨ�����췽����������Ĳ�ͬ
	String s = new String("hello");��String s = "hello"������?
	��һ����䴴�������������ڳ������д����ˡ�hello�����ڶ��д����ˡ�new String()��
	����s��ָ��new String()��������new Stringָ��hello��
	�ڶ�����䴴����һ�������ڳ������д����ˡ�hello��������sֱ��ָ��hello��

* String��StringBuffer��StringBuilder������
1)String���ݲ��ɱ䣬�����������ݿɱ䡣
2)StringBuffer��ͬ���ģ����ݰ�ȫ��Ч�ʵͣ���Щ������synchronized�����ˣ������ڶ��̣߳�
3)StringBuilder�ǲ�ͬ���ģ����ݲ���ȫ��Ч�ʸߣ������ڵ��̣߳��������õ���ࡣ

* StringBuffer��String�������βΣ�������������ԱȲ���

```java
public static void main(String[] args) {
   Student s1 = new Student("��",27);
   Student s2 = new Student("��",30);
   change1(s1,s2);
   System.out.println("s1:"+s1.getAge()+"---"+s1.getName());
   System.out.println("s2:"+s2.getAge()+"---"+s2.getName());
   System.out.println("--------change1������change2�����Ա�--------");
   Student s3 = new Student("��",35);
   Student s4 = new Student("��",32);
   change2(s3,s4);
   System.out.println("s3:"+s3.getAge()+"---"+s3.getName());
   System.out.println("s4:"+s4.getAge()+"---"+s4.getName());
}

private static void change2(Student s3, Student s4) {
	s3.setAge(100);//��s3�ĵ�ֵַ�����ݸ�ֵ
	s3.setName("��");//��s3�ĵ�ֵַ�����ݸ�ֵ
}

private static void change1(Student s1, Student s2) {
	s1 = s2;//��s2�ĵ�ֵַ��s1��Ҳ����˵s1��s2��ָ��s2ԭ���ĵ�ֵַ
	s1.setAge(100);//��s2ԭ���ĵ�ֵַ�����ݸ�ֵ
	s1.setName("��");//��s2ԭ���ĵ�ֵַ�����ݸ�ֵ	
}
```

## ��.Integer
* Integer i = 1; i += 1;������Щ����

```java
	Integer i = Integer.valueOf(3);//�Զ�װ��
	Integer a = new Integer(3);
	Integer b = 3;                  // ��3�Զ�װ���Integer����
	int c = 3;
	System.out.println(a == b);     // false ��������û������ͬһ����
	System.out.println(a == c);     // true a�Զ������int
	System.out.println(b == c);     // true a�Զ������int
	System.out.println(i == a);     // false
	System.out.println(i == b);     // true
	System.out.println(i == c);     // true 
	
	
	Integer f1 = 100, f2 = 100, f3 = 150, f4 = 150;

	//���������������ֵ��-128��127֮�䣬��ô����new�µ�Integer���󣬶���ֱ�����ó������е�Integer����
	//����f1==f2�Ľ����true����f3==f4�Ľ����false��
	System.out.println(f1 == f2);   //true
	System.out.println(f3 == f4);   //false
```

## ��.Short
* short s1 = 1; s1 = s1 + 1;�д���?short s1 = 1; s1 += 1;�д���
	����short s1 = 1; s1 = s1 + 1;����1��int���ͣ����s1+1������Ҳ��int �ͣ���Ҫǿ��ת�����Ͳ��ܸ�ֵ��short�͡�
	��short s1 = 1; s1 += 1;������ȷ���룬��Ϊs1+= 1;�൱��s1 = (short)(s1 + 1);������������ǿ������ת����
	
## ��.Math
* Math.round(11.5) ���ڶ��٣�Math.round(-11.5)���ڶ��٣�
	Math.round(11.5)�ķ���ֵ��12��Math.round(-11.5)�ķ���ֵ��-11��
	���������ԭ�����ڲ����ϼ�0.5Ȼ�������ȡ����



