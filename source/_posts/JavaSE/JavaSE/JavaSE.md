---
title: JavaSE
date: 2019-04-02 14:03:25
tags: JavaSE
categories:
  - Java
---

## java基础知识笔记

+ java中定义变量格式报错： float f = 1999.99； 因为默认的浮点为double类型，这样会丢失精度，编译报错！需强制转换
+ 语句System.out.println(1+2+"java"+3+4)输出的结果是 3java34
+ java中每种数据类型都是固定大小，故生成的程序不区分32位和64位。
+ ``` 
    // Java中break配合标记可以跳出**外层**for循环
    import java.util.Random;
    public class Hello{
    public static void main(String[] args) {
		int i, j;  
		itcast: for (i = 1; i <= 9; i++) {  
			for (j = 1; j <= i; j++) {  
				if (i > 2) {  
                    System.out.print("break\n"); 
					break itcast;  
				}
			}
		}
	    System.out.print("#\n"); 
    }
  ```
+ 在Java中定义时类的修饰符可以有 public、default（缺省）、protected、private,
  [为何Java在定义时需要类的修饰符啊？C++中定义类时不需要]
+ 在Java中，类只支持单继承，不允许多继承，也就是说一个类只能有一个直接父类。
+ 在子类中，访问父类中的成员变量格式：
  ```
    super.父类中的成员变量
	```
+ 抽象方法定义的格式：
	```
	public abstract 返回值类型 方法名(参数);
    ```
+ 抽象类定义的格式：
	```
	abstract class 类名 {
	}
	```
#	抽象类的细节问题

+ 1、抽象类一定是个父类？	
    是的，因为不断抽取而来的。
+ 2、抽象类中是否可以不定义抽象方法？
    是可以的，那这个抽象类的存在到底有什么意义呢？不让该类创建对象,方法可以直接让子类去使用
+ 3、抽象关键字abstract不可以和哪些关键字共存？	
   + 1、private：私有的方法子类是无法继承到的，也不存在覆盖，而abstract和private一起使用修饰方法，abstract既要子类去实现这个方法，而private修饰子类根本无法得到父类这个方法。互相矛盾。
   + 2、final，暂时不关注，后面学
   + 3、static，暂时不关注，后面学
