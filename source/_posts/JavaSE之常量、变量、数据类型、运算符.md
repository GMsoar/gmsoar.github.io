---
title: JavaSE之常量、变量、数据类型、运算符
date: 
tags: [变量,常量,数据类型,运算符]
categories: JavaSE
---

# N0.1 基本概念

***

## 关键字的研究

### 什么是关键字？

>1.关键字其实就是一些英文单词，是sun公司自己占用的，具有特殊含义和特殊功能以及特殊用途的。
>
>2.注意：关键字不能被程序员拿来定义类名，方法名或者变量名称等。

### 识别关键字

> * 关键字一般会高亮
> * 随自己接触Java知识的加深，以后自己就能辨别

## 标识符的研究

### 什么是标识符？

>1.标识符是Java中为类名或者变量名称或者方法名称等命名的规范。（程序员必须遵循这个规范）

### 标识符的组成规范

> 1.一般是由字符（一般是英文，中文也可以但是不规范），数字，下划线，美元符$组成
> 2.强制性要求：数字不能开头。
> 3.区分大小写的。 abc Abc是不一样的。
> 4.标识符不能是关键字。

## 常量的概念和使用

### 什么是常量？

> * 是指在Java程序中固定不变的数据，常量是一旦确定了值就无法改变的。
> * 就是实际生活中的一些确定值：3.14 , 100 , "迪丽热巴", true , false 

### 常量有哪些？

<table>
    <th>常量的分类</th>
    <th>示范</th>
    <tr>
        <td>整数常量</td>
        <td>100，0，2</td>
    </tr>
    <tr>
        <td>小数常量</td>
        <td>3.14，99.8，88.8</td>
    </tr>
    <tr>
        <td>字符常量</td>
        <td>'A'，'b'，'8'，'中' (只能是单个字符必须用单引号围起来)</td>
    </tr>
    <tr>
        <td>字符串常量</td>
        <td>"我是中国人"，"12345"，"abcde" (必须用双引号围起来)</td>
    </tr>
    <tr>
        <td>布尔常量</td>
        <td>true，false (真或假)</td>
    </tr>
    <tr>
        <td>空常量</td>
        <td>null</td>
    </tr>
</table>

***
# No.2 变量的基本概念

***

## 变量的概念和定义

### 什么是变量?
>变量是内存中的一块区域，其值在一定范围内可以发生改变的量。
>可以把变量理解成一个瓶子，只能装一个特定类型的数据。

### 变量的作用?
>可以在程序执行的过程中，存储数据，操作数据，传输数据，分析数据等。都需要用变量存储这个数据。

### 如何定义变量？

>变量的定义格式 ： **数据类型 变量名称 = 初始值**;

>**格式解析：**
> * 数据类型: 申明变量存储数据的具体类型，什么类型的变量就只能存放什么类型的数据。
> * 变量名称：变量必须有名字别人才可以使用和访问，变量的名字的首字母应该小写。满足“驼峰模式”， stuAge className	
> * 初始值：可有可无，但是必须与数据类型保持一致。什么类型的变量存储什么类型的数据。

```java
/*示例*/
public class VariableDemo01{
	public static void main(String[] args){
		// 数据类型 变量名称 = 初始值;
        int age = 22 ; // 变量的类型int整型，age是变量的名称 22是初始值  =是赋值 	
		System.out.println(age); // 22	
		
		age = 100 ; 
		System.out.println(age); // 100	
	}
}
```
## 数据类型的概念

**`引入变量的格式：数据类型 变量名称 = 初始值`**

### 数据类型到底有哪些
>* Java的数据类型大体分为2大类：**基本数据类型**，**引用数据类型**。

1. 基本数据类型(4大类8大种)
<table style="text-align:left">
    <th>类型</th>
    <th>对应为</th>
    <th>数据范围</th>
    <th>占用内存</th>
    <tr>
        <td>整数类型</td>
        <td>byte<br>short<br>int(默认)<br>long</td>
        <td>-128~127<br>-32768~32767<br>-2^31~2^31-1<br>-2^63~2^63-1</td>
        <td>1字节<br>2字节<br>4字节<br>8字节</td>
    </tr>
    <tr>
        <td>浮点型(小数)</td>
        <td>float(单精度)<br>double(默认双精度)</td>
        <td>1.4E-45~3.4028235E38<br>4.9E-324~1.7976931348623157E308<br></td>
        <td>4字节<br>8字节<br></td>
    </tr>
    <tr>
        <td>字符型</td>
        <td>char</td>
        <td>\u0000(即为0)<br>\uffff(即为65,535)<br></td>
        <td>2字节</td>
    </tr>
    <tr>
        <td>布尔型</td>
        <td>boolean</td>
        <td>true<br>false</td>
        <td>未定</td>
    </tr>
</table>
2. 引用数据类型：数组，类，接口等，只要不是基本数据类型那么就是引用数据类型

### 数据大小单位的换算

>计算机的底层都是二进制：0 ，1 开关。
>一个开关只能表示2种信息。男女  
>二个开关可以表示4个信息。

>计算机认为8个开关是8位，一个开关称为1位。一位叫1b.
>1个字节等于8位，字节的单位的B , 位的但是b.
>1B = 8b
>1K = 1024 = 2^10
>/-------------------------------------------
>>1KB = 1024B = 1024*8个开关。
>>1MB = 1024*1024B
>>1GB = 1024 *1024*1024B = 1024MB
>>1TB = 1024*1024 *1024*1024B = 1024GB

>**TIP**:
>开发中我们还是会选择用int定义整型，（默认）。
>开发中我们还是会选择用double定义小数，（默认）。

```java
    /*示例*/
    public class VariableDemo02{
	public static void main(String[] args){
		// 数据类型 变量名称 = 初始值;
		// 1.字节型
		byte age1 = 23;
		byte age2 = 127;
		//byte age3 = 128; // 报错，越界了， -128-127
		System.out.println(age1); // 23
		System.out.println(age2); // 127
		
		// 2.短整型 
		short st = 2333;
		System.out.println(st);
		
		// 3.整型 
		int money = 10000000;
		System.out.println(money);
		
		long lg = 232323233;
		System.out.println(lg);
		
		// 4.长整型 
		/** 注意语法：随便写一个整数常量，默认是int类型的
		    323232323232332323其实是int类型的，323232323232332323虽然没有超过long的范围，但是它超过了int的范围
			所以报错，那么如果希望随便写一个整数常量默认是long类型的，需要在整数后面加上L或者l.
		*/
		long nums = 323232323232332323L;
		System.out.println(nums);
		
		// 5.单精度小数 
		/** 注意语法：随便写一个小数常量，默认是double类型的
		    5.33其实是double类型的,如果希望随便写一个小数默认是float类型就应该在小数后面加上F或者f
			所以 */
		float ft = 5.33F;
		System.out.println(ft);
		
		// 6.双精度小数
		double db = 3.14 ;
		System.out.println(db);
		
		// 7.布尔型
		boolean flag1 = true ;
		boolean flag2 = false ;
		System.out.println(flag1);
		System.out.println(flag2);
		
		// 8.字符类型的变量 
		char c1 = 'a';
		char c2 = '中';
		char c3 = '中国'; // 直接报错!
		System.out.println(c1);
		System.out.println(c2);
		
	}
}
```

### 变量的使用注意事项

> 1.变量必须定义才可以使用。变量的作用从定义开始到 **}** 结束
> 2.同一个范围内不能定义两个同名的变量名称。冲突！！

```java
/*示例*/
public class VariableDemo03{
	public static void main(String[] args){
		//System.out.println(age); // 报错!!
		// 变量的作用从定义开始到}结束
		int age = 12 ;
	
		System.out.println(age);
		//int age = 100 ; // 报错
		
		{
			int num = 111;
			System.out.println(num);
		}
		// System.out.println(num); // 报错
	}
}
```
## 数据类型转换-自动类型转换

**前言**
>Java认为不同的变量和常量在一起运算后的结果的类型必须统一。
>所以**不同类型之间是存在类型转换的。**

数据类型的转换方式：
（1）自动类型转换。
（2）强制类型转换。
（3）表达式的自动类型提升。

#### 自动类型转换的语法规则：

> * 数据如果在变量的类型范围之内是可以直接自动类型转换的。
> * 小范围类型的变量可以自动类型转换给大范围类型的变量
>> 类型范围：由小到大
			byte -> short -> char -> int -> long  -> float  -> double

```java
/*示例*/
public class DataConvert{
	public static void main(String[] args){
		//  a.数据如果在变量的类型范围之内是可以直接自动类型转换的。
		byte bt = 120 ; // -128 - 127 自动类型转换
		//byte bt1 = 130 ; // 报错
		System.out.println(bt);
		
		//  b.小范围类型的变量可以自动类型转换给大范围类型的变量
		byte age = 23 ;
		int it = age ;  // 自动类型转换
		System.out.println(age); // 23
		System.out.println(it);  // 23 
		
	}
}
```

## 数据类型转换-强制类型转换

#### 强制类型转换的语法规则：

>* 数据超过了对应变量的类型范围就必须进行手工的强制类型转换，否则代码报错！！
>>
>* 大范围类型的变量赋值给小范围类型的变量必须进行手工强制类型转换，否则代码报错！

#### 强制类型转换的格式:
> **数据类型 变量 = (数据类型)数据或者变量**

>**TIP**:
>强制类型转换可能出现数据失真（数据溢出）
>
>小数强制转换成整数，会直接截断小数部分，保存整数结果。

```java
public class DataConvert{
	public static void main(String[] args){
		// a.数据超过了对应变量的类型范围就必须进行手工的强制类型转换，否则代码报错！！
		// byte bt = 127 ; // 没有问题，进行自动类型转换。
		// 数据类型 变量 = (数据类型)数据或者变量;	
		byte bt = (byte)200 ;
		System.out.println(bt);	 // -56 强制类型转换可能出现数据溢出，数据会失真!!	
		
		// b.大范围类型的变量赋值给小范围类型的变量必须进行手工强制类型转换，否则代码报错！
		int it = 30;
		byte rs = (byte)it ; // 强制类型转换
		System.out.println(rs); // 30
		
		// 拓展：
		double money = 99999.999;
		int it1 = (int)money;
		System.out.println(it1); // 结果是一个整数，小数强制转换成整数，会直接截断小数部分，保存整数结果。
	}
}
```

## 数据类型转换-表达式的自动类型提升

#### 表达式的自动类型提升语法规则：

表达式：**就是有+ - * / 以及变量和常量一起运算**

>表达式的最终结果类型是**由表达式中的最高数据类型决定**的，
>最高数据类型是什么，最终结果的数据类型就是什么。

>在表达式中，**byte short , char是直接提升成int运算的**
byte ， short ，char  ->  int -> long  -> float  -> double

```java
/*示例*/
public class DataConvert{
	public static void main(String[] args){
		byte b1 = 1 ;
		short b2 = 2;
		int b3 = 3 ;
		int rs = b1 + b2 - b3 ;
		System.out.println(rs);
		
		byte c1 = 10 ;
		int c2 = 100 ;
		float ft = 1.0F ;
		double rs1 = c1*c2 + ft + 1.0; 
		System.out.println(rs1);
		
		
		// 面试题：
		byte a1 = 10 ;
		byte a2 = 100 ;
		// byte a3 = a1 + a2 ; // 代码会报错!在表达式中，byte short , char是直接提升成int运算的
		int rs2 = a1 + a2 ;
		System.out.println(rs2);
		
	
		
		byte bt1 =  1 ;
		byte b12 = 2
		double rs3 = bt1 + bt2 + 1.0;
	}
}
```
## ASCLL编码表

* 计算机的底层是不能存储字符的。计算机的底层都是硬件。
* 计算机的底层只能存储二进制。0 1
* 2个开关可以表示4个信息
* 8个开关可以表示256个信息。

>二进制就是整数

>110 = 0*2^0 + 1*2^1 + 1*2^2 = 6
>
>00 = 0
>01 = 1^2^0 = 1
>10 = 0*2^0 + 1*2^1 = 2
>11 = 1*2^0 + 1*2^1 = 3

**<u>字符在底层存储的就是二进制。</u>**

>美国人：
>为自己国家的字符做存储机制。
>美国人用每8个开关存储一个字符就够了。对于美国人来说够用了。

| 字符| 对应整数|
|-------|--------|
|A      |    65  |
|B      |    66  |
|C      |    67  |
|a      |    97  |
|b      |    98  |
|c      |    99  |
|0      |    48  |

<b>这套编码规则称为ASCII编码表。</b>

>**TIP:**
>字符在计算机底层其实就是一个编号。完全可以把字符当整数用。
>char的范围是小于int范围的。

```java
public class ASCIIDemo{
	public static void main(String[] args){
			int rs = 'a' ; // 'a'的范围小于int,自动类型转换，把a字符的编号交给了int类型的变量rs.
			System.out.println(rs); // 97
			
			
			int rs1 = 'A';
			System.out.println(rs1);
			
			int rs2 = '磊';
			System.out.println(rs2); // 30922 
			
			//30922如何转换成字符呢
			int code = 30923;
			char c = (char)code;  // 把编号恢复成字符！！
			System.out.println(c);
	}
}
```

## 运算符的研究

### 什么是运算符

>是对常量和变量进行运算的符号。
>运算符在表达式中经常使用。

### Java的运算符有哪些

> 1.算术运算符
> 2.赋值运算符
> 3.比较运算符
> 4.三元运算符

**算术运算符：+ ， - ， * ， / ， % ， ++ ，--**

>基本的算术运算符：+，-，*，/，% (取余)

>自增自减运算符：++(自增), --(自减)
>
>>++ , -- 用在变量的运算上的，可以对变量进行+1 , -1
>>++ , -- 在与变量单独运算的时候，放在变量的前后是没有区别的。都是对变量进行+1和-1操作。
>
>>++ ， -- 在表达式中与变量运算的时候，放在变量前后是有差别的。
>
>>在表达式中，++，--如果放在变量的前面，会先对变量进行+1或者-1然后再拿变量的值进行运算。
>
>>在表达式中，++，--如果放在变量的后面，会先拿变量的值进行运算，然后再对变量的值进行+1或者-1

```java
/*示例*/
public class OperatorDemo02{
	public static void main(String[] args){	
		 /** 自增自减运算符: ++（自增） , --（自减）  */
		 int a = 10 ;
		 a++ ; // 原理：a = a + 1
		 System.out.println(a); //11
		 
		 int b = 10 ;
		 b-- ; // b = b -1 
		 System.out.println(b); //9
		 
		 
		 int i = 10 ;
		 ++i ; // i = i+ 1
		 System.out.println(i); //11
		 
		 
		 int j = 10 ;
		 --j ; // j = j -1 
		 System.out.println(j); //9
		 
		 System.out.println("--------------------------------拓展------------------------------------");
		 /**
		 	  c.++ ， -- 在表达式中与变量运算的时候，放在变量前后是有差别的。
		      在表达式中，++，--如果放在变量的前面，会先对变量进行+1或者-1然后再拿变量的值进行运算。
		      在表达式中，++，--如果放在变量的后面，会先拿变量的值进行运算，然后再对变量的值进行+1或者-1
		 */
		 int m = 10 ;
		 int rs = m++ ;  // 先用再加
		 System.out.println(rs);  // 10
		 System.out.println(m);   // 11
		 
		 int n = 10 ;
		 int rss1 = ++n ;  // 先加再用
		 System.out.println(rss1); // 11
		 System.out.println(n); //  11
		 
		 System.out.println("--------------------------------拓展：面试题------------------------------------");
		 int k = 3 ;
         int p = 4 ;
		 // k 3  4  3  2  3
		 // p 4  5  6
		 // rs1     4  -  3  -  5  +  6  - 3   -  3  +1 - 3
         int rs1 = ++k - --k - ++p + ++p - k-- - ++k + 1 -k;		 
		 System.out.println(rs1); // -6
		 System.out.println( k); // 3
		 System.out.println( p); // 6
		 
	}
}
```

### +符号在字符和字符串中的操作

**总规则：**
>+符号与字符串运算的时候是用作连接符的。
+符号与任何字符串连接的结果依然是一个字符串。
整数与字符做运算的直接拿值运算。不会做连接了！

>**TIP:**
>能算则算，不能算就连接！！！！

```java
/*示例*/
public class OperatorDemo03{
	public static void main(String[] args){
		int a = 5 ;
		// + 遇到字符串表示连接
		System.out.println("abc" + 'a');     // abca
		System.out.println("abc" + a);       // abc5
		System.out.println("abc" + 5 + 'a');   // abc5a
		System.out.println(15 + "abc" + 15); // 15abc15
		System.out.println(a + 'a'); // 5 + 97  = 102  运算，单个字符就是整数。
		System.out.println(a + 'a' + "Dlei"); // 102Dlei 
	}
}
```

### 赋值运算符

>基本的赋值运算符：=

>扩展的赋值运算符：+= , -= , *= , /= , %= 
>注意：扩展运算符自带强制类型转换
>a += b ;   // 公式： a = (a的数据类型) (a+b);
>a -= b ;   // 公式： a = (a的数据类型) (a-b);
>a *= b ;   // 公式： a = (a的数据类型) (a*b);
>a /= b ;   // 公式： a = (a的数据类型) (a/b);
>a %= b ;   // 公式： a = (a的数据类型) (a%b);

```java
/*示例*/
public class OperatorDemo04{
	public static void main(String[] args){
		int age = 12 ; // =就是赋值运算符，从右往左执行！
		
		int a = 10 ;
		int b = 20 ;
		//int rs = a + b;
		//a+=b ; // a = (a的类型)(a+b); 
		//a*=b ; // a = (a的类型)(a*b); 
		//a%=b ; // a = (a的类型)(a%b);    10 % 3 = 1    25 % 3 = 1  10 % 20 = 10    
		a /= b ; // a = (a的类型)(a /b) 
		System.out.println(a); 
	}
}
```

### 比较运算符

> **比较运算符又叫关系运算符，是两个数据之间进行比较的运算，运算结果都是布尔值`true`或者`false` 。**

>**符号:**
> \>
> \>=
> \<\
> \<=\
> \==
> \!=

>**TIP:**
>1. 判断是否相等必须是“==”。不是“=”
>
>2. 比较运算符的结果一定是布尔类型的结果。false ，true

```java
/*示例*/
public class OperatorDemo05{
	public static void main(String[] args){
	    // 做判断 
		int a = 10 ;
		int b = 11 ;
		System.out.println(a > b); // false
		System.out.println(a >= b); // false
		System.out.println(a < b); // true
		System.out.println(a <= b); // true
		System.out.println(a == b); // false 是否相等
		System.out.println(a != b); // true 是否不相等
		
		System.out.println("--------------------");
		int a1 = 10 ;
		int b1 = 10 ;
		System.out.println(a1 > b1); // false
		System.out.println(a1 >= b1); // true
		System.out.println(a1 < b1); // false
		System.out.println(a1 <= b1); // true
		System.out.println(a1 == b1); // true 是否相等
		System.out.println(a1 != b1); // false 
		
		System.out.println("--------------------");
		int c1 = 10 ;
		int c2 = 20 ;
		System.out.println(c1 = c2); // 20 ,这里在赋值输出，不是判断是否相等！
		
	}
}
```

```java
/**
   运算符的练习题**
   随便给你一个三位数，计算出它的个位，十位，和百位并输出显示。
   898 
*/
public class ExecDemo09{
	public static void main(String[] args){
		int num = 898 ;
		// 输出个位
		System.out.println("个位："+num % 10) ; // 8
		// 输出十位
		System.out.println("十位："+ (num / 10) % 10); // 9
		// 输出百位
		System.out.println("百位："+ num / 100); // 8.98 -> 8
		
	}
}
```