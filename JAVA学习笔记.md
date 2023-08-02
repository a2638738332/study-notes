---



---

# JAVA学习笔记【基础】

## DAY 1

### 笔记

#### 快捷键

**//放大字体： ctrl+ +**
**// alt+/  手动提示**
**// syso+手动提示 自动补全代码**
**// ctrl+/ 单行注释**
**// ctrl+shift+/ 单行注释**
**// 复制上一行ctrl+alt+方向键下**
**// 删除行 ctrl+D**
**// 补全代码： ctrl+2  l**
**// 移动代码 ： alt+方向键下**

### 作业

#### int(32位) float(32位)    long（64位）double(64位)互相转化的情况

```java
public class DAY1 {
    public static void main(String[] args) {
        int a=1000000000;
        float a1=1000000000.1111f;
        long b=1000;
        double b1=1000.111d;
        a=(int)a1;
        System.out.println(a);
        a=1000000000;
        a1=100000000000000000000000000000000000000.999999999999999999999999999999999999999999999999999f;
        b=1000;
        b1=1000.111d;
        a1=a;
        System.out.println(a1);
        a=100;
        a1=100.11f;
        b=1000000000;
        b1=1000000000.111d;
        b=(long)b1;
        System.out.println(b);
        a=100;
        a1=100.11f;
        b=1000000000;
        b1=1000000000000000000000000.111d;
        b1=b;
        System.out.println(b1);

    }

}

```

结果![image-20220830191856995](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220830191856995.png)



## DAY 2

### 笔记

#### 源码 反码 补码

| 原码 | 3    |      |      |      | 0    | 0    | 0    | 0    | 0    | 0    | 1    | 1    |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|      | -3   |      |      | 1    | 0    | 0    | 0    | 0    | 0    | 1    | 1    |      |
| 反码 | 3    |      |      |      | 0    | 0    | 0    | 0    | 0    | 0    | 1    | 1    |
|      | -3   |      |      | 1    | 1    | 1    | 1    | 1    | 1    | 0    | 0    |      |
| 补码 | 3    |      |      |      | 0    | 0    | 0    | 0    | 0    | 0    | 1    | 1    |
|      | -3   |      |      | 1    | 1    | 1    | 1    | 1    | 1    | 0    | 1    |      |



### 作业

#### 1.使用循环嵌套打印以下九九乘法表内容

```java
public class DAY2 {
    public static void main(String[] args) {
        new DAY2().text();

    }
    public void text(){
        int i;
        int j;
        int sum;
        for(i=1;i<=9;i++){
            for(j=1;j<=i;j++){
                System.out.print(i+"*"+j="+(i*j)+"\t");
            }
            System.out.println("\n");
        }
    }
}
```

结果·![](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220901112100445.png)

####  2.使用循环嵌套打印以下图案内容

```java
    public void text1(){
        int i;
        int j;
        int x;
        for (i=1;i<=5;i++){
            for(j=1;j<=5-i;j++){
                System.out.print(" ");
            }
            for (x=1;x<=i;x++){
                System.out.print("* ");
            }
            System.out.println();
        }
        for (i=1;i<=4;i++){
            for(j=1;j<=i;j++){
                System.out.print(" ");
            }
            for (x=5-i;x>=1;x--){
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```

结果![image-20220901093831129](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220901093831129.png)

#### 3.编写程序实现根据用户输入的分数，输出对应的成绩等级信息。当输入分数值为负数，程序停 止。提示用户输入错误分数。

```java
 public void text3() {
        Scanner reader = new Scanner(System.in);
        System.out.println("请输入你的分数");
        int i = reader.nextInt();
            if (i > 90) {
                System.out.println("优");
            } else if (i <= 90 && i >= 80) {
                System.out.println("良");
            } else if (i <= 80 && i > 60) {
                System.out.println("中");
            } else if (i <= 60 && i >= 0) {
                System.out.println("不及格");
            } else {
                System.out.println("您输入的信息有误，请从新输入");
            }

        }
```

结果![image-20220901100046884](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220901100046884.png)

#### 4.编写程序实现打印0-1000数字内，个位十位和百位都相同的数字，例如：111,222,333

```java
  public void text4(){
        int i=0;

        for(i=1;i<=1000;i++){
            int b=i/100;
            int s=(i-((i/100)*100))/10;
            int g=i%10;
            //System.out.println(b+" "+s+" "+g);
            if(b==s&&s==g&&b==g){
                System.out.println("\t\t"+i);
            }
        }
    
```

结果![image-20220901102822781](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220901102822781.png)

#### 5.判断101-200之间有多少个素数，并输出所有素数。(只能被1和它本身整除的自然数为素数)

```java
public void test5(){
    int i;
    int j;
    int sum=0;
    int num=0;
    for (i=101;i<=200;i++){
        for (j=1;j<=i;j++){
           sum=i%j;
            //System.out.println(sum);
           if (sum==0){
               num++;
               //System.out.println(num);
           }

        }
        if (num==2){
            System.out.println(i);

        }
        num=0;
    }
}
```

结果![image-20220901110039813](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220901110039813.png)

## DAY 3

### 笔记

#### 冒泡排序

例如，实现一个方法，参数是int[]，该方法可以对数组进行排序，使用【冒泡排序】，该方法不需要返 回值。 规则：在一组数据中，从左到右，俩俩比较，然后把较大的数据往前推，一轮下来之后，最大的一个数 据就被推到了最右边。

例如： 2 1 4 9 8 5 3 

第一轮第1次比较后 1 2 4 9 8 5 3 

第一轮第2次比较后 1 2 4 9 8 5 3 

第一轮第3次比较后 1 2 4 9 8 5 3

第一轮第4次比较后 1 2 4 8 9 5 3 

第一轮第5次比较后 1 2 4 8 5 9 3 

第一轮第6次比较后 1 2 4 8 5 3 9

```java
//冒泡排序
public void test(int[] arr){
//获取到数组的长度
int len = arr.length;
//外层循环控制一共比较几轮
for(int i=0;i<len-1;i++){
//内层循环控制每轮比较多少次数，每轮比较的次数是有变化的
for(int j=0;j<(len-i-1);j++){
//比较俩个相邻数据的大小
//如果前一个数据比后一个数据大
if(arr[j]>arr[j+1]){
//交互这个俩个数据的位置
arr[j] = arr[j] ^ arr[j+1];
arr[j+1] = arr[j] ^ arr[j+1];
arr[j] = arr[j] ^ arr[j+1];
}
}
//这个输出，可以看到每一轮比较结束后的结果是怎样的
System.out.println("\t"+Arrays.toString(arr));
}
}    
    
```

#### 异或交换两个的数据位置

arr[j] = arr[j] ^ arr[j+1];
arr[j+1] = arr[j] ^ arr[j+1]; 
arr[j] = arr[j] ^ arr[j+1];

原理

arr[j] = arr[j] ^ arr[j+1];
arr[j+1] = arr[j] ^ arr[j+1]^ arr[j+1];
arr[j] = arr[j] ^ arr[j+1] ^ arr[j] ^ arr[j+1]^ arr[j+1];

### 作业

## DAY 4

### 笔记

#### 选择排序

例如，实现一个方法，参数是int[],该方法可以对数组进行排序，使用【选择排序】，该方法不需要返回 值。 规则：每一轮在待排序的区域中比较找到一个最小值后，把这个最小值放到已经排好顺序的区域的末 尾，剩下的部分，组成一个新的待排序部分，重复上面的步骤直到排序结束。

假设待排序的数组为：2 1 4 9 8 5 3 

第一轮从待排序区中找到一个最小值，然后和第一个位置的数字交互位置 1 2 4 9 8 5 3 

第二轮从新的待排序区中找到一个最小值，然后和第二个位置的数字交互位置 1 2 4 9 8 5 3

第三轮从新的待排序区中找到一个最小值，然后和第三个位置的数字交互位置 1 2 3 9 8 5 4 

第四轮从新的待排序区中找到一个最小值，然后和第四个位置的数字交互位置 1 2 3 4 8 5 9

第五轮从新的待排序区中找到一个最小值，然后和第五个位置的数字交互位置 1 2 3 4 5 8 9 

第六轮从新的待排序区中找到一个最小值，然后和第六个位置的数字交互位置 1 2 3 4 5 8 9

```java
public static int[] text7(int[] b){
    int min_In;
    int min_Find;
    for (int i = 0; i < b.length-1; i++) {
        min_In=i;
        min_Find=i;
        for (int j = i+1; j < b.length; j++) {
            if(b[j]<b[min_In]){
                min_In=j;
            };
        }
        if (min_Find!=min_In){
            int mind=b[min_Find];
            b[min_Find]=b[min_In];
            b[min_In]=mind;
        }
    }

    return b;
}
```

### 作业

## DAY 5

### 笔记

#### **创建和初始化对象的过程：**

 **Student s = new Student(); 以这句代码为例进行说明：** 

**对Student类进行类加载，同时初始化类中静态的属性赋默认值，给静态方法分配内存空间 执行类中的静态代码块 堆区中分配对象的内存空间，同时初始化对象中的非静态的属性赋默认值 调用Student的父类构造器 对Student中的属性进行显示赋值，例如 public int age = 20; 执行匿名代码块 执行构造器代码 =号赋值操作，把对象的内存地址赋给变量s**

#### 接口

**接口是除了类和数组之外，另外一种引用数据类型 接口和类不同，类的内部封装了成员变量、构造方法和成员方法，而接口的内部主要就是封装了方法和 静态常量。**

**注意1， 定义类使用关键字 class ，定义接口使用关键字 interface **

**注意2，接口中的属性都是公共的静态常量 注意：常量的名字一般需要全大写 **

**注意3，接口中的方法都是抽象方法 **

**注意：JDK8中，还允许在接口中编写静态方法和默认方法 **

**注意：JDK9中，还允许在接口中编写私有方法 **

**注意4，接口的中抽象方法，不需要使用 abstract 修饰符，因为接口中的方法默认就是抽象方法**

#### 内部类

成员内部类：

1.一个类中定义一个非静态修饰的内部类，可以使用任意访问全权限

2.成员内部中不能定义静态的属性和方法

3.成员内部类访问外部类所有的属性和方法

​      静态：类名，静态成员

​      非静态：类名，this，非静态成员

## DAY 6

### 作业 

#### **1.根据以下描述，进行代码分析和结构设计 一个公司，每个员工都有俩个相同的行为，上班和下班。同时，员工又分很多种，例如，销售、管理、 后勤。每个不同的工作岗位，都需要工作，但工作内容是不一样的**

public class  公司{



}

class 员工{

public 上班（）{

}

public 工作（）{

}

public 下班（）{

}

}

重写。。。。

#### **2.接口与抽象类的区别**

接口和类不同，类的内部封装了成员变量、构造方法和成员方法，而接口的内部主要就是封装了方法和 静态常量。

#### **3.根据以下表述完成程序编程 鸟类可以飞翔，飞机类也可以飞翔，那么可以把飞翔这个动作抽象出来，抽象到一个抽象类或者接口 中，然后让鸟类和飞机类去继承或实现，那么这里是把方法抽象到父类型中，还是抽象到接口中？**

```java
public interface Fly {
     public void fly();
}
class test{
    public static void main(String[] args) {
        Fly f=new Fly() {
            @Override
            public void fly() {
                System.out.println("我会飞");
            }
        };
        f.fly();
        Fly d=new Fly() {
            @Override
            public void fly() {
                System.out.println("我也会飞");
            }
        };
        d.fly();
    }



}
```

#### **4.利用接口做参数，写个计算器，完成加减乘除运算的功能 要求 （1）：定义一个接口Compute含有一个方法 double computer(double n, double m) （2）：设计四个类分别实现此接口，完成加减乘除运算 （3）：设计一个类UseCompute，类中含有方法： public void useCom(Compute com, double num1, double num2) ，此方法能够用传递过来的对象调用computer方法完成运算，并输出运算的结果 （4）：设计一个主类Test，调用UseCompute中的方法useCom来完成加减乘除运算**

```java
 interface Compute {
    double computer(double n,double m);
}
class add implements Compute{

    @Override
    public double computer(double n, double m) {
        return n+m;
    }
}
 class subtract implements Compute{

     @Override
     public double computer(double n, double m) {
         return n-m;
     }
 }
 class ride implements Compute{

     @Override
     public double computer(double n, double m) {
         return n*m;
     }
 }
 class divide implements Compute{

     @Override
     public double computer(double n, double m) {
         return n/m;
     }
 }
 class UseCompute{
    public void useCom(Compute com,double num1,double num2){
        System.out.println(com.computer(num1,num2));
    }
 }
 public class Test{
     public static void main(String[] args) {
         UseCompute use=new UseCompute();
         use.useCom(new subtract(),2,3);
         use.useCom(new ride(),2,3);
         use.useCom(new divide(),2,3);
         use.useCom(new add(),2,3);

     }
 }
```

#### **5.请描述各个权限修饰符的作用**

**public** > protected > default > private

public，公共的，在所有地方都可以访问

**protected**，受保护的，当前类中、子类中，同一个包中其他类中可以访问   **default**，默认的，当前类中、同一个包中的子类中可以访问 注意，default默认的，指的是空修饰符，并不是default这个关键字 例如，String name; 在类中，这种情况就是默认的修饰符 

**private**，私有的，当前类中可以访问

| 修饰符    | 类中 | 同包非子类 | 同包子类 | 不同包子类 | 不同包非子类 |
| --------- | ---- | ---------- | -------- | :--------- | ------------ |
| public    | Y    | Y          | Y        | Y          | Y            |
| protected | Y    | Y          | Y        | Y          | N            |
| default   | Y    | Y          | Y        | N          | N            |
| private   | Y    | N          | N        | N          | N            |

#### **6.按照要求，补齐代码，要求在控制台输出 HelloWorld**

```java
interface Inter {
    void show();
}
class Outer {
public static Inter method(){
    Inter in=new Inter() {
        @Override
        public void show() {
            System.out.println("Hello Would");
        }
    };
    return in;
}
}
public class OuterDemo {
    public static void main(String[] args) {
        Outer.method().show();
    }
}
```

#### **7.将以下接口进行实现，并完成规定的功能**

```java
public interface Action{
    public String[] test(String str);
}
class Test1{
    Action m1(){
        Action act=new Action() {
            @Override
            public String[] test(String str) {
                char atr[]=str.toCharArray();
                for (int i = 0; i < atr.length; i++) {
                    if (i!=atr.length-1) {
                        System.out.print(atr[i] + "|");
                    }else {
                        System.out.println(atr[i]);
                    }
                }
                str=atr.toString();
                return new String[0];
            }
        };
        return act;
    }
    Action m2(){
        Action act=new Action() {
            @Override
            public String[] test(String str) {
                char atr[]=str.toCharArray();
                for (int i = 0; i < atr.length; i++) {
                    if (i!=atr.length-1) {
                        System.out.print(atr[i] + "-");
                    }else {
                        System.out.println(atr[i]);
                    }
                }
                str=atr.toString();
                return new String[0];
            }
        };
        return act;
    }
    public static void main(String[] args) {
        Test1 st=new Test1();
        st.m1().test("abc");
        st.m2().test("abc");
    }
}
```

## DAY 7

### 笔记

#### **Collection**

List：有序，可重复，可以使用索引

ArrayList：底层使用数组实现，增删慢，查找快

LinkedList：底层使用链表实现，增删快，查找慢

Vector：底层使用数组实现，增删慢，查找快，线程安全

Set：无序，不可重复，不可以使用索引

HashSet：底层使用HasMap实现，依靠hashCode和equel去重，靠着hashCode和equals方法来判断对象是否重复。

### 作业

#### 基本数据的包装类分别是什么？

![image-20220915182253886](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220915182253886.png)

#### String类型如何转换为基本数据类型？

#### 基本数据类型如何转换为String类型？

#### 判断下列代码的输出结果

```java
public static void main(String[] args) {
    Integer i1 = 10;
    Integer i2 = new Integer(10);
    Integer i3 = 10;
    Integer i4 = Integer.valueOf(10);
    Integer i5 = new Integer(10);
    Integer i6 = 128;
    Integer i7 = 128;
    System.out.println("(i1==i2) = " + (i1 == i2));
    System.out.println("(i1==i3) = " + (i1 == i3));
    System.out.println("(i2==i5) = " + (i2 == i5));
    System.out.println("(i3==i4) = " + (i3 == i4));
    System.out.println("(i6==i7) = " + (i6 == i7));
}
```

(i1==i2) = false
(i1==i3) = true
(i2==i5) = false
(i3==i4) = true
(i6==i7) = false

### ==和equals()的区别？

**一个是判断地址，一个是判断内容**

### 编写一个圆类（Circle），该类中含有属性：半径。创建两个Circle对象，利用equals方法判断半径是否 相等，利用toString（）方法输出其信息



```java
public class Circle {
    private int radius;

    Circle(int radius) {
        this.radius=radius;
    }

    public int getRadius() {
        return radius;
    }

    public void setRadius(int radius) {
        this.radius = radius;
    }

    @Override
    public String toString() {
        return "radius=" + radius ;
    }
}
class Test{
    public static void main(String[] args) {
        Circle circle=new Circle(2);
        Circle circle1=new Circle(3);
        System.out.println(circle.equals(circle1));
        System.out.println(circle.toString());
        System.out.println(circle1.toString());
    }
}
```

## DAY 8

### 笔记

#### 获得Class的三种方式

Class c1 = Student.class;

Class c2 = Class.forName("com.briup.demo.Student");

Student stu = new Student(); Class c3 = stu.getClass();

#### 获取类中声明的属性

**获取类中的public修饰的属性，也包含从父类中继承过来的public属性**

```java
Field[] getFields() 
```

```java
Field getField(String name)
```

**获取类中声明的属性（包含私有的），但是不能获取从父类中继承过来的属性**

```java
Field[] getDeclaredFields() 

Field getDeclaredField(String name)
```



### 作业

#### 1.定义一个方法可以遍历输出Collection集合，并且消除泛型警告 ，遍历集合中存放的类型为Number类 型及子类型

```java
public class zy1 {
    public static void main(String[] args) {
        ArrayList<Number> collection= new ArrayList<>();
        collection.add(1);
        collection.add(2);
        collection.add(3);
        collection.add(4);
        collection.add(5);
        collection.add(6);
        zy1 coll= new zy1();
        coll.traverse(collection);
    }
    public void traverse(ArrayList<Number> collection) {
        for(int i=0;i<collection.size();i++){
            System.out.println(collection.get(i).toString());
        }
    }

}
```

#### 2.定义一个通用的(带泛型)的方法，该方法可以返回Collection集合中的最大值

```java
public class zy2 {
    public static void main(String[] args) throws Exception {
        Collection<Number> collection = new ArrayList<>();
        collection.add(1);
        collection.add(2);
        collection.add(3);
        collection.add(4);
        collection.add(5);
        collection.add(6);
        zy2 zy2 = new zy2();
        System.out.println(zy2.max(collection));
    }
    public <number extends Number> int max(Collection<number> collection){
        int max=0;
        for(number number:collection){
            if(number.intValue()>max){
                max=number.intValue();
            }
        }
        return max;
    }
}
```

## DAY 9

### 笔记

#### 单例模式

```java
//饿汉式
public class tt1 {
    private static tt1 t1=new tt1();
        private tt1(){}
        public static tt1 gettt1(){
            return t1;
        }

}
//懒汉式
class lan{
    private static lan lan1=null;
    private lan(){}
    static public lan getlan1(){
        if (lan1==null)
         lan1=new lan();
        return lan1;
    }
}
class test{
    public static void main(String[] args) {
        tt1 t2=tt1.gettt1();
        tt1 t3=tt1.gettt1();
        System.out.println(t2==t3);
        lan l1=lan.getlan1();
        lan l2=lan.getlan1();
        System.out.println(l2==l1);
    }
}
```

### 作业

#### java中Throwable下的主要子类有（包括间接继承的子类）

**Error**

**Exception**

**RantimeExceptio**n

#### Error和Exception区别？

**Error ，表示错误情况，一般是程序中出现了比较严重的问题，并且程序自身并无法进行处理。 Exception ，表示异常情况，程序中出了这种异常，大多是可以通过特定的方式进行处理和纠正 的，并且处理完了之后，程序还可以继续往下正常运行**。

#### 运行时异常和编译时异常的区别？

**编译时异常，继承自 Exception 类，也称为checked exception，编译器在编译期间，会主动检查这种异 常，发现后会报错，并提示我们要对这种异常进行处理。 运行时异常，继承自 RuntimeException 类，也称为unchecked exception，编译器在编译期间，不会检 查这种异常，也不要求我们去处理，但是在运行期间，代码中可能会抛出这种类型的异常。**

#### 写出5种常见的运行时异常

**ArithmeticException 算数异常**

**ClassCastException 类型转换异常**

**ArraylndexOutOfBoundsException 数组越界异常**

**NumberFormatException 数字格式化异常**

**NullPointerException 空指针异常**

#### 使用catch(Exception e)的好处是

**try-catch 语句块，就是用来对指定代码，进行异常捕获处理，并且处理完成后，JVM不会停止运行， 代码还可以正常的往下运行！**

#### catch语句中异常的排列方式是什么

**这种异常处理方式，要求多个catch中的异常不能相同，并且如果catch中的多个异常之间有 子父类异 常的关系的话，那么子类异常要求在上面的catch处理，父类异常在下面的catch处理。 因为如果父类型异常再最上面的话，下面catch语句代码，永远不会被执行**

#### 写DivisionByZero类，完成下列要求 （1） 定义division()方法：要求执行10/0操作，并使用异常处理机制处理可能会产生的异常 main()：调用division() （2）修改division()：执行10/0不变，但不在方法中处理产生的异常，改将异常抛出 修改main()：调用division()并处理其抛出的异常

（1）

```java
public class Division {
    static public void division() throws ArithmeticException{
        try {
            int a=10/0;
            System.out.println(a);
        }catch (ArithmeticException e){
            System.out.println("算数异常");
        }

    }

    public static void main(String[] args) throws ArithmeticException {
        Division.division();
    }
}
```

(2)

```java
public class Division {
    static public void division() throws ArithmeticException{
            int a=10/0;
            System.out.println(a);
    }

    public static void main(String[] args) {
        try{
            Division.division();
        }catch (ArithmeticException e){
            System.out.println("算术异常");
        }

       
    }
}
```

#### 分析下列代码运行结果

```java
class ReturnExceptionDemo {
    public static void methodA() throws Exception {
        try {
            System.out.println("进入方法A");
            throw new Exception("制造异常"); //手动抛出异常
        } finally {
            System.out.println("用A方法的finally");
        }
    }
    public static int methodB() {
        try {
            System.out.println("进入方法B");
            return 1;
        } finally {
            System.out.println("用B方法的finally");
            return 2;
        }
    }
    public static void main(String[] args) {
        try {
            methodA();
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
        int i = methodB();
        System.out.println(i);
    }
}
```

进入方法A
用A方法的finally
制造异常
进入方法B
用B方法的finally
2

```java
class Return1 {
    public static void main(String[] args) {
        int i = new Return1().testReturn1();
        System.out.println(i);
    }
    private int testReturn1() {
        int i = 1;
        try {
            i++;
            System.out.println("try:" + i);
            return i;
        } finally {
            i++;
            System.out.println("finally:" + i);
        }
    }
}
```

try:2
finally:3
2

```java
class Return2 {
    public static void main(String[] args) {
        System.out.println(testReturn2());
    }
    private static List<Integer> testReturn2() {
        List<Integer> list = new ArrayList<>();
        try {
            list.add(1);
            System.out.println("try:" + list);
            return list;
        } finally {
            list.add(3);
            System.out.println("finally:" + list);
        }
    }
}
```

try:[1]
finally:[1, 3]
[1, 3]

```java
class Return3 {
    public static void main(String[] args) {
        System.out.println(testReturn3());
    }
    private static String testReturn3() {
        String a = "hello";
        try {
            a += "!";
            System.out.println("try:" + a);
            return a;
        } finally {
            a += "world";
            System.out.println("finally:" + a);
        }
    }
}
```

try:hello!
finally:hello!world
hello!

## DAY 10

### 笔记

#### **线程状态变化情况**

![](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220923092004020.png)

#### join方法                            

join() ：WATTING

当前线程进入阻塞，只有等到调用join方法的线程执行完毕，当前线程才可以继续执行

join(毫秒级参数) TIMEWATTNG

当前线程进入阻塞，只有等到调用join方法的线程时间结束，当前线程才可以继续执行

### 作业

#### 什么是线程？

线程是进程中的一个代码执行单元，负责当前进程中代码程序的执行，一个进程中有一个或多个线程。 当一个进程中启动了多个线程去分别执行代码的时候，这个程序就是多线程程序

#### CUP中的时间片，有什么作用

时间片，当前一个线程要使用CPU的时候，CPU会分配给这个线程一小段时间（毫秒级别），这段时间 就叫做时间片，也就是该线程允许使用CPU运行的时间，在这个期间，线程拥有CPU的使用权。

#### 进程和线程的关系是什么

进程里面有很多线程

#### 并发和并行的概念是什么

线程的并发执行，是指在一个时间段内，俩个或多个线程，使用一个CPU，进行交替运行。

线程的并行执行，是指在同一时刻，俩个或多个线程，各自使用一个CPU，同时进行运行。

#### 多线程的好处

速度更快

#### 线程安全指什么

一个线程的执行不会影响的其他线程的内容的变化

#### 一个类中的main方法中的代码，是由哪一个线程执行的

main线程

#### 线程的状态有哪些

NEW  新建

RUNNABLE 可运行

BLOCKED 锁阻塞

WAITING 无限 期等待

TIMED_WAITING 有限期等待

TERMINATED 终止 （死 亡）

#### 线程有哪些分类

前台线程和后台线程

#### 设置线程优先级的方法是什么

t1.setPriority(Thread.MAX_PRIORITY);

#### 使用多线程，在子线程中输出1-100之间的偶数，主线程输出1-100 之间的奇数

```java
public class Test3 {
    public static void main(String[] args) {
        Test3.t1();
        Thread t=new Thread(){
            @Override
            public void run() {
                Test3.t2();
            }
        };

        t.start();

    }

    public static void   t1(){
        for (int i = 0; i < 100; i++) {
            if (i%2!=0){
                System.out.print(i+"\t");
            }
        }
        System.out.println();
    }
    public static void   t2(){
        for (int i = 0; i < 100; i++) {
            if (i%2!=0){
                System.out.print(i+"\t");
            }
        }
        System.out.println();
    }

}
```

#### 怎么获取一个线程的名字、

String name = Thread.currentThread().getName();

#### 请描述start方法和run方法的区别

start是开启一个新的线程

run是正常调用方法



#### 有以下代码

```Java
class ThreadTest {
    public static void main(String[] args) {
        Thread t = new Thread() {
            @Override
            public void run() {
                String name = Thread.currentThread().getName();
                System.out.println(name);
            }
        };
        t.start();
//         t.run();
    }
}
```

#### 请分别说明，调用t.start()和调用t.run()方法后，程序的输出结果是什么

## DAY 11

### 笔记

### 作业

#### 编写一个简单的线程代码，运行的时候，查看这个线程状态所经历的状态，并输出这些状态

```java
public class Test {
    public static void main(String[] args) {
        Thread t=new Thread(new Runnable() {
            @Override
            public void run() {
                for (int i = 0; i < 10; i++) {

                }
            }
        });
        System.out.println(t.getState());
        t.start();
        for (int i = 0; i < 20; i++) {
            System.out.println(t.getState());
        }
    }
}
```

#### 尝试写一个死锁的例子

```java
public class Testi4 {
    public static void main(String[] args) {
        Object obj=new Object();
        Object obj1=new Object();
        Thread t=new Thread(){
            @Override
            public void run() {
                synchronized (obj) {
                    try {
                        Thread.sleep(20);
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                    synchronized (obj1){

                  }
                }
              }
        };
        Thread t2=new Thread(){
            @Override
            public void run() {
                synchronized (obj1) {
                    try {
                        Thread.sleep(20);
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                    synchronized (obj){

                 }
                }
            }
        };
        t.start();
        t2.start();
    }
}
```

#### 线程A中执行线程B的join()方法会产生什么效果？

停止执行线程A,等待线程B执行完在继续执行线程A

#### 线程A通过调用什么方法来中断其阻塞状态？

 **阻塞1**，线程运行时，调用sleep或者join方法后，进入这种阻塞，该阻塞状态可以恢复到RUNNABLE 状态，条件是线程被打断了、或者指定的时间到了，或者join的线程结束了

 **阻塞2**，线程运行时，发现锁不可用后，进入这种阻塞，该阻塞状态可以恢复到RUNNABLE状态，条 件是线程需要争夺的锁对象变为可用了（别的线程把锁释放了）

 **阻塞3**，线程运行时，调用了wait方法后，线程先释放锁后，再进入这种阻塞，该阻塞状态可以恢复 到BLOCKED状态（也就是阻塞2的情况），条件是线程被打断了、或者是被别的线程唤醒了（notify 方法）

#### 画出线程状态图（包含切换状态的方法）



#### 什么方法返回当前线程的引用？

```
Thread.currentThread().getName()
```

#### 创建一个线程程序，将该线程睡眠，并且打断睡眠状态，查看是否被打断

```java
public class Test5 {
    public static void main(String[] args) throws InterruptedException {
        Thread t=new Thread(){
            @Override
            public void run() {

                    try {
                        Thread.sleep(100000);
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                    System.out.println("进程t结束");
                }

        };
        System.out.println(t.getState());
        t.start();
        for (int i = 0; i <100 ; i++) {
            System.out.println(t.getState());
        }
        Thread.sleep(50);
       t.interrupt();
    }
}
```

#### 现在有T1、T2、T3三个线程，怎样保证T2在T1执行完后执行，T3在T2执行完后执行?

 join方法的使用

```java
public class Test6 {
    public static void main(String[] args) {
        Object obj = new Object();
        Object obj1 = new Object();
        Object obj2 = new Object();
        Thread t1 = new Thread() {
            @Override
            public void run() {
                System.out.println("线程一先执行");
            }
        };
        Thread t2 = new Thread() {
            @Override
            public void run() {
                try {
                    t1.join();
                } catch (InterruptedException e) {
                    throw new RuntimeException(e);
                }
                System.out.println("线程二在执行");
            }
        };
        Thread t3 = new Thread() {
            @Override
            public void run() {
                try {
                    t2.join();
                } catch (InterruptedException e) {
                    throw new RuntimeException(e);
                }
                System.out.println("线程三最后执行执行");
            }
        };
        t1.start();
        t2.start();
        t3.start();
    }
}
```

#### 编写程序，创建线程A，让其进行休眠，然后在主线程中，将线程A进行打断，观察线程A的运行情况，并说出线程A所经历的状态都有哪些

```java
public class Test5 {
    public static void main(String[] args) throws InterruptedException {
        Thread t=new Thread(){
            @Override
            public void run() {

                    try {
                        Thread.sleep(100000);
                    } catch (InterruptedException e) {
                        throw new RuntimeException(e);
                    }
                    System.out.println("进程t结束");
                }

        };
        t.start();
        Thread.sleep(500);
       t.interrupt();
    }
}
```

NEW

RUNNABLE

TIMED_WAITING

#### 描述synchronized修饰静态方法和非静态方法的区别

synchronized 关键字修饰非静态方法，默认使用 this 当做锁对象，并且不能自己另外指定 synchronized 关键字修饰静态方法，默认使用 当前类的Class对象 当做锁对象，并且不能自己另外指 定

#### 在 Java 程序中怎么保证多线程的运行安全

加锁

#### wait()方法和sleep()方法的区别

wait在有锁的情况下才能使用，只能用在锁的代码块中，wait之后进入等待池，只有被唤醒，ontify唤醒之后才能进入锁池

sleep是让线程睡眠固定的时间，时间结束后继续进行，可以被interrupt进行打断。

#### 编写两个线程,一个线程打印1-52的整数，另一个线程打印字母A-Z。打印顺序为12A34B56C….5152Z。即按照整数和字母的顺序从小到大打印，并且每打印两个整数 后，打印一个字母，交替循环打印，直到打印到整数52和字母Z结束

```java
public class Test7 {
    public static void main(String[] args) {
        Object obj=new Object();
        Thread t=new Thread(){
            @Override
            public void run() {
                synchronized (obj){
                    for (int i = 1; i < 53; i++) {
                        System.out.print(i+" ");
                        if (i%2==0){
                            obj.notify();
                            try {
                                obj.wait();
                            } catch (InterruptedException e) {
                                throw new RuntimeException(e);
                            }
                        }
                    }
                    //obj.notify();
                }
            }
        };
        Thread t1=new Thread(){
            @Override
            public void run() {
                synchronized (obj){
                    for (int i=65;i<91;i++){
                        System.out.print((char) i+" ");
                        obj.notify();
                        try {
                            obj.wait();
                        } catch (InterruptedException e) {
                            throw new RuntimeException(e);
                        }
                    }
                }
            }
        };
        t.start();
        t1.start();
    }

}
```

## DAY 12

### 笔记

java中常用的流及其关系结构

![image-20220926152619136](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20220926152619136.png)

#### 字节流

#####  控制台

使用字节流，从控制台读取数据，以及向控制台中写数据。

```java
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;

public class Test1 {
    public static void main(String[] args) throws IOException {
        //声明流
        InputStream is=null;
        OutputStream os=null;
        //创建流
        is=System.in;
        os=System.out;
        int date=-1;
        byte[] b1=new byte[128];
            date = is.read(b1);
            os.write(b1, 0, date);
            os.flush();



        //关闭输入输出流
        is.close();
        os.close();
    }
}
```

##### 字节数组

使用字节流，从字节数组中读取数据，以及向字节数组中写数据。

 **java.io.ByteArrayInputStream** 负责从字节数组中读取数据 

**java.io.ByteArrayOutputStream** 负责把数据写入到字节数组中

```java
import java.io.*;
import java.util.Arrays;

public class Test2_1 {
    public static void main(String[] args) {
        byte[] b1="hello,would".getBytes();
        InputStream in=new ByteArrayInputStream(b1);
        OutputStream ou=new ByteArrayOutputStream();

        int len=-1;
        byte[] by =new byte[1024];
        try {
            len=in.read(by);
            ou.write(by,0,len);
            byte[] bb=((ByteArrayOutputStream) ou).toByteArray();
            System.out.println(Arrays.toString(bb));
        } catch (IOException e) {
            throw new RuntimeException(e);
        }

    }
}
```

##### 管道

使用字节流，可以从管道中读取数据，以及向管道中写数据。

**java.io.PipedInputStream** 负责从管道中读取数据 

**java.io.PipedOutputStream** 负责将数据写入到管道中

```java
import java.io.IOException;
import java.io.PipedInputStream;
import java.io.PipedOutputStream;
import java.util.Arrays;

public class Test31 {
    public static void main(String[] args) {
        try {
            PipedInputStream in=null;
            PipedOutputStream out=null;
            in=new PipedInputStream();
            out=new PipedOutputStream(in);
            Thread t1=new Wirth("t1",out);
            Thread t2=new Read1("t2",in);
            t1.start();
            t2.start();
            try {
                t1.join();
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
            try {
                t2.join();
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        } catch (IOException e) {
            throw new RuntimeException(e);
        }


    }
}
class Wirth extends Thread{
    PipedOutputStream out;
    public Wirth(String name,PipedOutputStream out){
        super(name);
        this.out=out;
    }
    @Override
    public void run() {
        byte[] b1="Hello Would".getBytes();
        try {
            out.write(b1);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }finally {
            try {
                out.close();
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
class Read1 extends Thread{
    PipedInputStream in;
    public Read1(String name,PipedInputStream in){
        super(name);
        this.in=in;
    }
    @Override
    public void run() {
        int len=-1;
        try {
            in.read();
            byte[] b=in.readAllBytes();
            System.out.println(Arrays.toString(b));
        } catch (IOException e) {
            throw new RuntimeException(e);
        }finally {
            try {
                in.close();
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
```

### 作业

#### 两个线程循环打印A和B，例如线程A输出A，线程B输出B，依次按顺序循环输出 ABABABAB

```java
package zy;

public class zy3 {
    public static void main(String[] args) {
        Object obj=new Object();
        Thread t1=new Thread(){
            @Override
            public void run() {
                synchronized (obj) {
                    for (int i = 0; i < 20; i++) {
                        System.out.print("A");
                        obj.notify();
                        try {
                            obj.wait();
                        } catch (InterruptedException e) {
                            throw new RuntimeException(e);
                        }
                    }

                    obj.notify();
                }
            }
        };
        Thread t2=new Thread(){
            @Override
            public void run() {
                synchronized (obj){
                    for (int i = 0; i < 20; i++) {
                        System.out.print("B"+" ");
                        obj.notify();
                        try {
                            obj.wait();
                        } catch (InterruptedException e) {
                            throw new RuntimeException(e);
                        }
                        obj.notify();
                    }
                }
            }
        };
        t1.start();
        t2.start();
    }
}
```

#### 使用多线程，计算100万的阶乘

> 提示：任务拆分与汇总

```java
import java.math.BigInteger;

public class zy4 {
    public static void main(String[] args) {
        BigInteger a=new BigInteger("100000");
        BigInteger b=new BigInteger("200000");
        BigInteger c=new BigInteger("300000");
        BigInteger d=new BigInteger("400000");
        BigInteger e=new BigInteger("500000");
        BigInteger f=new BigInteger("600000");
        BigInteger j=new BigInteger("700000");
        BigInteger h=new BigInteger("800000");
        BigInteger i1=new BigInteger("900000");
        BigInteger g=new BigInteger("1000000");
        BigInteger ADD=BigInteger.ONE;
        BigInteger[] arr = new BigInteger[10];
        BigInteger SUM=new BigInteger("0");
        BigInteger sum =BigInteger.ZERO;

        Runnable r=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();
                for (BigInteger i = BigInteger.ONE; i.compareTo(a)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum1="+sum1.toString());
                arr[0]=sum1;
            }
        };
        Runnable r1=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i = a; i.compareTo(b)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum2="+sum1.toString());
                arr[1]=sum1;
            }
        };
        Runnable r2=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i = b; i.compareTo(c)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
               // System.out.println("sum3="+sum1.toString());
                arr[2]=sum1;
            }
        };
        Runnable r3=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();
                for (BigInteger i = c; i.compareTo(d)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum4="+sum1.toString());
                arr[3]=sum1;
            }
        };
        Runnable r4=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i = d; i.compareTo(e)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum5="+sum1.toString());
                arr[4]=sum1;
            }
        };
        Runnable r5=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i = e; i.compareTo(f)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum6="+sum1.toString());
                arr[5]=sum1;
            }
        };
        Runnable r6=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i = f; i.compareTo(j)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum7="+sum1.toString());
                arr[6]=sum1;
            }
        };
        Runnable r7=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i = j; i.compareTo(h)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum8="+sum1.toString());
                arr[7]=sum1;
            }
        };
        Runnable r8=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i = h; i.compareTo(i1)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum9="+sum1.toString());
                arr[8]=sum1;
            }
        };
        Runnable r9=new Runnable() {
            @Override
            public void run() {
                BigInteger sum1=BigInteger.ONE;
                String name=Thread.currentThread().getName();

                for (BigInteger i =i1; i.compareTo(g)<1; i=i.add(BigInteger.ONE)) {
                    sum1=sum1.multiply(i);
                    //System.out.println(name+" "+sum1.toString());
                }
                //System.out.println("sum10="+sum1.toString());
                arr[9]=sum1;
            }
        };


        Thread t1=new Thread(r,"t1");
        Thread t2=new Thread(r1,"t2");
        Thread t3=new Thread(r2,"t3");
        Thread t4=new Thread(r3,"t4");
        Thread t5=new Thread(r4,"t5");
        Thread t6=new Thread(r5,"t6");
        Thread t7=new Thread(r6,"t7");
        Thread t8=new Thread(r7,"t8");
        Thread t9=new Thread(r8,"t9");
        Thread t10=new Thread(r9,"t10");
        t1.start();
        t2.start();
        t3.start();
        t4.start();
        t5.start();
        t6.start();
        t7.start();
        t8.start();
        t9.start();
        t10.start();
        try {
            Thread.sleep(1000*30);
        } catch (InterruptedException ex) {
            throw new RuntimeException(ex);
        }
        /*for (int i = 0; i < 10; i++) {
            System.out.println("sum"+i+"="+arr[i]);
        }*/
        for (int i = 0;  i<10; i++) {
            ADD=ADD.multiply(arr[i]);
        }
        System.out.println("ADD="+ADD);
    }
}
```

#### java 中有几种类型的流？JDK 为每种类型的流提供了一些抽象类以供继承，请说出他们分别是哪些类？

输入流，输出流

字节流 ，字符流

InputStream ，代表字节输入流类型 

OutputStream ，代表字节输出流类型 

Reader，代表字符输入流类型 

Writer ，代表字符输出流类型

#### 如何列出某个目录下的所有文件？

```java
list()

listFiles()
```



#### 如何列出某个目录下的所有子目录？

```java
list()

listFiles()
```



#### 如何判断一个文件或目录是否存在？

```java
 exists() 
```



#### 拷贝一张图片，从一个目录到另外一个目录下

```java
package zy;

import java.io.*;

public class zy1 {
    public static void main(String[] args) {
        File f1=new File("C:\\wx\\ly\\ly.jpg");
        File f2=new File("D:\\WX\\ly.jpg");
        try {
            InputStream in=new FileInputStream(f1);
            OutputStream out=new FileOutputStream(f2);
            byte[] b=new byte[9999999];
            try {
                in.read(b);
                out.write(b);
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        } catch (FileNotFoundException e) {
            throw new RuntimeException(e)
        }


    }
}
```

## DAY  13

#### 字符流和字节流有什么区别

字符流十已字符为单位，字节流是已字节为单位。

#### 编程实现：如果现在有一款只能试用10次的软件，超过10次之后就需要提醒用户购买 正版软件。（程序运行一次，使用次数就要减一次）

>#### 提示：将试用的次数写到.txt中对其进行读取，将每次读取到次数减一然后再写到其.txt中,直至试用次数没有

```java
package zy;

import java.io.*;
import java.util.Arrays;

public class zy1 {
    public static void main(String[] args) throws IOException {
        int i=0;
        String str="a";
        File file=new File("C:\\Users\\26387\\Desktop\\DD.txt");
        FileWriter wir=new FileWriter(file,true);
        FileReader red=null;
       red=new FileReader(file);
       int len=-1;
       char[] c1=new char[1];
       while ((len=red.read(c1))!=-1){
           i++;
       }
       i=10-i;
            wir.write(str);
            wir.close();


       if (i<=0){
           System.out.println("试用天数已经用完");
       }else if(i>0){
            System.out.println("试用天数还剩"+i+"天");
        }

    }


}
```

#### 编程实现：线程A，从控制台读取用户输入的内容，并且把内容写入到管道流中。线程B，从管道流中读取内容，并且把内容再写入到一个本地文件中。

```java
package zy;

import java.io.*;
import java.util.Arrays;
import java.util.Scanner;

public class zy2 {
    public static void main(String[] args) {
        PipedReader red=null;
        PipedWriter wit=null;
        red=new PipedReader();
        wit=new PipedWriter();
        try {
            red.connect(wit);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
        Thread t1=new WIT(wit);
        Thread t2=new RED(red);
        t1.start();
        t2.start();
        try {
            t1.join();
            t2.join();
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
    }

}
class RED extends Thread{

    PipedReader red=null;
     RED(PipedReader red){
        this.red=red;
    }
    @Override
    public void run() {
        File file=new File("C:\\Users\\26387\\Desktop\\TT.txt");
        FileWriter f1=null;
        try {
             f1=new FileWriter(file);
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
        int len=-1;
        try {
            while ((len=red.read())!=-1){
                System.out.write(len);
                f1.write(len);
                f1.flush();
                System.out.flush();

            }
            red.close();
        } catch (IOException e) {
            throw new RuntimeException(e);
        }finally {
            try {
                red.close();
                f1.close();
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
class WIT extends Thread{
    Scanner reader=new Scanner(System.in);
    PipedWriter wit=null;
    WIT(PipedWriter wit){
        this.wit=wit;
    }
    @Override
    public void run() {

        String str=reader.nextLine();
        char[] c1=str.toCharArray();
        try {
            for (int i = 0; i <c1.length ; i++) {
                wit.write(c1[i]);
                wit.flush();
            }
        }
        catch (IOException e) {
            throw new RuntimeException(e);
        }finally {
            try {
                wit.close();
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
```

#### 递归实现输入任意目录，列出文件以及文件夹

```java
jpackage zy;

import java.io.File;
import java.util.Scanner;

public class zy3 {
    public static void main(String[] args) {
        Scanner reader=new Scanner(System.in);
        String str=reader.nextLine();
        File f=new File(str);
        test(f);
    }
    public static void test(File f){
        String[] str1=f.list();
        for (int i = 0; i < str1.length; i++) {
            System.out.println(str1[i]);
        }
    }

}
```

#### 统计一个txt文件中字母'A'和'a'出现的总次数

```java
package zy;

        import java.io.*;
        import java.util.Scanner;

public class zy4 {
    public static void main(String[] args) throws IOException {
        Scanner reader=new Scanner(System.in);
        String str=reader.nextLine();
        int a=0;
        int A=0;
        File file=new File("C:\\Users\\26387\\Desktop\\TT.txt");
        FileWriter wit=null;
        FileReader red=null;
        wit=new FileWriter(file);
        red=new FileReader(file);
        wit.write(str);
        wit.flush();
        int len=-1;
        while((len=red.read())!=-1){
            if ((char)len == 'a') {
                a++;
            }else if ((char)len=='A'){
                A++;
            }
        }
        System.out.println("a的个数为:"+a);
        System.out.println("A的个数为:"+A);

    }
}
```

## DAY 14

### 作业

有如下类：

```Java
public class Trader {
    private final String name;
    private final String city;

    public Trader(String name, String city) {
        this.name = name;
        this.city = city;
    }

    public String getName() {
        return name;
    }

    public String getCity() {
        return city;
    }

    @Override
    public String toString() {
        return "Trader{" + "name='" + name + '\'' + ", city='" + city + '\'' + '}';
    }
}
```

```Java
public class Transaction {
    private final Trader trader;
    private final int year;
    private final int value;

    public Transaction(Trader trader, int year, int value) {
        this.trader = trader;
        this.year = year;
        this.value = value;
    }

    public Trader getTrader() {
        return this.trader;
    }

    public int getYear() {
        return this.year;
    }

    public int getValue() {
        return this.value;
    }

    public String toString() {
        return "{" + this.trader + ", " + "year: " + this.year + ", " + "value:" + this.value + "}";
    }
}
```



创建集合：

```Java
class Test {
    public static void main(String[] args) {
        Trader raoul = new Trader("Raoul", "Cambridge");
        Trader mario = new Trader("Mario", "Milan");
        Trader alan = new Trader("Alan", "Cambridge");
        Trader brian = new Trader("Brian", "Cambridge");
        List<Transaction> transactions = Arrays.asList(
                new Transaction(brian, 2011, 300),
                new Transaction(raoul, 2012, 1000),
                new Transaction(raoul, 2011, 400),
                new Transaction(mario, 2012, 710),
                new Transaction(mario, 2012, 700),
                new Transaction(alan, 2012, 950)
        );
    }
}
```

使用Stream完成下列问题：

(1)找出2011年发生的所有交易，并按交易额排序（从低到高）。
(2) 交易员都在哪些不同的城市工作过？
(3) 查找所有来自于剑桥的交易员，并按姓名排序。
(4) 返回所有交易员的姓名字符串，按字母顺序排序。
(5) 有没有交易员是在米兰工作的？
(6) 打印生活在剑桥的交易员的所有交易额。
(7) 所有交易中，最高的交易额是多少？
(8) 找到交易额最小的交易。

```java
ist<Transaction> collect = transactions.stream().filter(e -> e.getYear() == 2011).sorted((o1, o2) -> o1.getValue() - o2.getValue()).collect(Collectors.toList());
for (Transaction a:collect){
    System.out.println(a);
}
System.out.println();
List<String> collect1 = transactions.stream().map(e -> e.getTrader()).map(e -> e.getCity()).distinct().collect(Collectors.toList());
for (String a:collect1){
    System.out.println(a);
}
System.out.println();
List<String> cambridge = transactions.stream().filter(e -> e.getTrader().getCity().equals("Cambridge")).map(e -> e.getTrader().getName()).distinct().sorted().collect(Collectors.toList());
System.out.println(cambridge);
System.out.println();
String collect2 = transactions.stream().map(e -> e.getTrader()).map(e -> e.getName()).distinct().sorted().collect(Collectors.joining("-"));
System.out.println(collect2);
System.out.println();
List<String> collect3 = transactions.stream().filter(e -> e.getTrader().getCity() == "Milan").map(e -> e.getTrader()).map(e -> e.getName()).distinct().collect(Collectors.toList());
System.out.println(collect3);
System.out.println();
List<Integer> collect4 = transactions.stream().filter(e -> e.getTrader().getCity() == "Cambridge").map(e -> e.getValue()).collect(Collectors.toList());
System.out.println(collect4);
System.out.println();
Optional<Integer> max = transactions.stream().map(e -> e.getValue()).max(Integer::compareTo);
System.out.println(max);
System.out.println();
Optional<Transaction> min = transactions.stream().min((o1, o2) -> o1.getValue() - o2.getValue());
System.out.println(min);
```

# Linux学习笔记

## 笔记



## 作业

### 作业1

1.查看当前用户下的隐藏文件,并显示详细信息。

ls -a -l

2.创建一个新用户,并设置密码。

sudo useradd -mk /home/swift -s /bin/bash swift

sudo passwd swift

3.创建a.txt文件,属主有读写执行权限,属组,有读写,其他账户无权限

chmod 760 a.txt

### 作业2

1.创建a.txt,b.txt,c.txt,ab.txt,abc.txt
2.创建目录 game1,game2,game3,gbme1
3.查找a结尾的文件或文件夹
4.查找第2字符是b且以.txt结尾的文件
5.将a.txt 复制到game1文件夹中
6.将b.txt移动到gbme1文件夹中
7.查找以1结尾,倒数第4个字符是a的文件夹

ls *ab*.txt 、 ls*[ab]* 、 ls [ab].txt 分别代表什么
9.将/etc/passwd中的内容重定向到abc.txt中
10.清空abc.txt的内容
11.删除刚刚创建的文件和文件夹

​                     

# JAVA学习笔记【复习】

## 1.标识符，关键字，变量

<img src="C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20221010142918235.png" alt="image-20221010142918235" style="zoom:150%;" />

### 八种数据类型

byte shout int long float double char boolean

一个字节等于8位

| byte | shout | int  | long | float | double | boolean | char |
| :--: | :---: | :--: | :--: | :---: | :----: | :-----: | :--: |
|  1   |   2   |  4   |  8   |   4   |   8    |    1    |  2   |

## 2.操作符，流程控制

### 局部变量

局部变量没有默认值，所以使用时要赋值。

方法的参数，也是局部变量

### 实例变量

实例变量就是类中的属性，也叫成员变量（非静态的）

实例变量有默认值

实例变量作用在非静态的方法中

### 操作符

instanceof  判断对象是否属于指定类型



![image-20221010145129596](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20221010145129596.png)

算数右移是除以2的n次方

算数左移是乘以2的n次方

特殊情况

> 如果移动的位数超过了该类型的最大位数，那么编译器会对移动的位数取模/取余。如果对int型移动33位，实际上只移动了33%32=1位。如果对int型移动32位，实际上只移动了32%32=0位

### 位运算符



![image-20221010150016287](C:\Users\26387\AppData\Roaming\Typora\typora-user-images\image-20221010150016287.png)

都要满足才是1

一个满足就是1

相同为0，不同为1

如过是短路的&和|如果前面结果已经注定，呢么就不会往后执行，会直接结束

### 三目运算符

格式

```java
int a=10;
int b=20;
int z=(a>b)?a:b;
```

### 类型转换

基本数据类型转化

从低往高转会自动转换，也叫隐式转换，从高往低转换，需要强制类型转换，可能会丢失数据

> byte转int为自动转换（小转大）
>
> int转byte需要强制转换（大转小）
>
> 数据丢失的因为byte只能储存8位，int可以存32未，转换是只能保存前8位，所以数据会丢掉

引用类型数据转化

子类型转化为夫类型可以自动转化

夫类型转化为子类型需要强转

### 流程控制

在一个程序中，需要执行的代码，结构可分为三种

顺序

分支

if

switch

循环

for

while

do-while

break 满足一定条件直接结束循环或switch

continul 结束本次循环，直接进入下一次循环

label 可以给不同的循环加标签，配合break和contiunl可以指定结束那个循环

Random 随机数 参数传随机数范围

## 3.数组

数组拷贝的方法

在java.lang.System类中提供一个名为arraycopy的方法可以实现复制数组中元素的功能

```java
public int[] test(int[] a){
int[] b = new int[a.length*2];
System.arraycopy(a, 0, b, 0, a.length);
return b;
}
```

工具类

**toString方法**
可以把一个数组变为对应的String形式

**copyOf方法**
可以把一个数组进行复制
该方法中也是采用了arraycopy方法来实现的功能

**copyOfRange方法**
也是复制数组的方法，但是可以指定从哪一个下标位置开始复制
该方法中也是采用了arraycopy方法来实现的功能

**sort方法**
可以对数组进行排序

**binarySearch方法**
在数组中，查找指定的值，返回这个指定的值在数组中的下标，但是查找之前需要在数组中先进行
排序，可以使用sort方法先进行排序

**equals方法**
可以比较俩个数组是否相等,但是要求俩个数组中的值一一相等并且顺序也要一致才行，所以在比较
之前，我们最好是用sort方法对俩个数组先进行排序
第一个要求，俩个数组的元素个数相同
第二个要求，俩个数组的每个下标对应的数据相同

**fill**
可以使用一个特定的值，把数组中的空间全都赋成这个值
**asList**
可以把一组数据，封装到一个List集合中，并且把list集合对象返回。

```java
package 数组;

import java.util.Arrays;
import java.util.List;

public class T {
    public static void main(String[] args) {
        int[] a={1,2,5,40,90,76,13,4,};
        System.out.println(a.toString());
        System.out.println();
        System.out.println(Arrays.toString(a));
        System.out.println();
        int[] c=Arrays.copyOf(a,a.length);
        System.out.println(Arrays.equals(a, c));
        System.out.println();
        System.out.println(Arrays.toString(c));
        System.out.println();
        Arrays.sort(c);
        System.out.println(Arrays.toString(c));
        System.out.println();
        int i = Arrays.binarySearch(c,90);
        System.out.println(i);
        System.out.println();
        int[] b=new int[10];
        Arrays.fill(b,100);
        System.out.println(Arrays.toString(b));
        System.out.println();
        List<int[]> ints = List.of(b);
        for (int[] f:ints
             ) {
            System.out.println(Arrays.toString(f));
        }
        System.out.println(ints);


    }
```

## 4.类和对象

**类是对象的模板，对象是类的实体**

this关键字的使用场景： 

1. 区别成员变量和局部变量 

2. 调用类中的其他方法

3. 调用类中的其他构造器

   

调用类中的其他构造器：

```java
public class Student{
public String name;
public Student(){
//调用一个参数的构造器,参数的类型是String
this("tom");
}
public Student(String name){
this.name = name;
}
}
```

this关键字的意义：

this代表，所在类的当前对象的引用（地址值），即对象自己的引用。

## 5.封装、继承、多态

### 封装

在类中定义属性的时候，一般需要把属性隐藏起来。 如果外界需要访问这个属性，那么就提供公共方法对其访问

```java
public class Student{
//使用private关键字来修饰属性，不允许外部直接访问该属性
private String name;
//提供公共的setName方法，可以让外部调用该方法给name属性赋值
public void setName(String name){
this.name = name;
}
//提供公共的getName方法，可以让外部调用该方法获取name属性的值
public String getName(){
return name;
}
}
```

**private** 

private修饰符修饰的为私有的

只能在本类中访问

```java
public class Student{
//私有属性，只允许在当前类中访问，出了这个类的范围，就不能访问
private String name;
//私有方法，只允许在当前类中调用，出了这个类的范围，就不能调用
private void test(){
}
}
```

### 方法重载

必须在同一个类

参数不同

> 类型不同
>
> 数量不同
>
> 顺序不同

 方法的修饰符、返回类型、抛出异常这些地方没有限制

> 一般都会相同

特殊情况：

```java
public class Test{
注意，这时候， t.test(1,1) 代码是会编译报错的，因为类中定义的俩个方法都匹配
注意，当参数无法完全精确匹配到方法的时候，参数会尝试做自动转换，然后再去尝试匹配方法
例如，
虽然byte类型数据，可以自动转换为short，也可以转换为int，但是short离byte“更近”
3 创建和初始化对象
new Student()，该代码完成了俩个过程，对象的创建和初始化
例如，以下面代码为例进行说明
//方法重载
public void test(int a,long b){}
public void test(long b,int a){}
public static void main(String[] args){
Test t = new Test();
t.test(1,1L);//调用到第一个方法
t.test(1L,1);//调用到第二个方法
t.test(1,1);//问题：这个会调用到哪一个test方法？
}
}
```

> 因为类型会自动转化，所以两个方法都匹配，就会报错

```java
public class Test {
//重载方法1
public void test(int a){}
//重载方法2
public void test(short a){}
public static void main(String[] args){
Test t = new Test();
byte a = 1;
t.test(a);//这里会调用第二个方法，也就是short类型参数的test方法
}
}
```

> 这里会调用第二个方法
>
> 因为byte离shout更近

### 继承

继承的好处

> 提高代码从复用性

继承关键字 **extends**

子类继承父类，创建子类对象的时候，会先默认调用父类的构造器：

```java
//定义Person类，作为父类
public class Person{
public Person(){
System.out.println("Person类中的构造器被调用");
1
2
3
4
子类继承父类，会继承父类的属性和方法，那么就需要先调用父类的构造器对父类中的属性进行初
始化，初始化完成后再给子类使用。
构造器的作用之一就是进行初始化
6 super关键字
在类中，除了可以使用this关键字之外，还可以使用super关键字
在子类中，使用super关键字一般做以下事情：
访问父类中的属性
调用父类中的方法
调用父类中的构造器
访问父类中的属性：
}
}
//定义Student类，作为子类
class Student extends Person{
public Student(){
System.out.println("Student类中的构造器被调用");
}
}
public static void main(String[] args){
new Student();
}
```

#### super关键字

> 访问父类中的属性 
>
> 调用父类中的方法 
>
> 调用父类中的构造器

子类调用父类构造器，会自动调用，也可以自己写

**ps**. this 和super 不能同时调用构造器，会报错。

###  方法重写

**方法从写要满足以下条件**

> 方法名必须相同
>
> 参数列表必须相同
>
> 访问控制修饰符可以被扩大，但是不能被缩
>
> public > protected > default > private
>
> 方法抛出异常类型的范围可以被缩小，但是不能被扩大
>
> ClassNotFoundException --扩大--> Exception
>
> 返回类型可以相同，也可以不同
>
> 如果父类的返回类型是引用类型，子类重写后的方法返回类型可以和父类方法的返回类型保持 一致，也可以是父类方法返回类型的子类型
>
> 如果父类的返回类型是基本类型，那么子类重写后的返回类型必须和父类的保持一致 例如: 父类方法的返回类型是int，子类重写后的返回类也必须是int

**ps.**父类中的 静态方法和私有方法 ，子类无法重写。

> 子类继承父类，在调用方法的时候，如果子类中没用重写，那么调用的是从父类继承的方法，如果 子类重写了这个方法，那么将会调用到子类中重写后的方法。（ 非常重要 ）
>
> 

**instanceof**

多用在类型强制转换判断中，如果是子夫类关系，才能进行转换，否则运行是会报错。

# 数据库-Oracle学习笔记【基础】

## oracle（一） 概述、环境、sql、查询、条件

### 登录

管理员用户

```sql
sqlplus system/密码;
```

普通用户

```sql
sqlplus 用户名/密码;
```

查看当前登录账号

```sql
show user;
```

清屏

```sql
$cls;
```

退出当前用户

```sql
exit;
```

### 会话

改为英文会话

```sql
alter session set nls_language=english;
```

改为中文会话

```sql
alter session set nls_language='simplified chinese';
```

### 用户

创建用户（需要管理员权限）

```sql
create user 用户名 identified by 密码;
```

给用户权限

```sql
grant connect,resource to 用户名;
```

这里角色代表相关权限的集合：

**connect** 角色，基本的连接 

**resource** 角色，程序开发 

**DBA** 角色，数据库管理

切换用户

```sql
conn 用户名/密码;
```

删除用户

```sql
drop user 用户名 cascade;
```

### 导入

导入表

```sql
@"表的绝对路径"
```

查看用户有哪些表

```sql
select table_name from user_tables;
```

查看表结构

```sql
desc 表名;
```

### SQL

**SQL语言属于第四代编程语言**

> 第一代编程语言，机器语言，是面向机器的，通过二进制代码对其计算机操作 
>
> 第二代编程语言， 汇编语言，使用指令对应的符号，来代替二进制代码 
>
> 第三代编程语言，高级开发语言 ，例如C、C++ Java等，语言更加简单，操作更方便 
>
> **第四代编程语言，只告诉计算机需要做什么，不需要告诉计算机怎么做，更加接近自然语言**

**sql语句的分类**

> **DQL** (Data Query Language)，数据查询语言 用于检索数据库中的数据，主要是 SELECT 语句 
>
> **DML** (Data Manipulation Language)，数据操纵语言 用于改变数据库中的数据，主要是 INSERT , UPDATE , DELETE 语句; 
>
> **DDL**（Data Define Langage)，数据定义语言 用来建立、修改、删除数据库对象，主要是 CREATE 、 ALTER 、 DROP 、 TRUNCATE 语句 
>
> **TCL** (Transaction Control Language)，事务控制语言 用于维护数据的一致性，主要是 COMMIT , ROLLBACK , SAVEPOINT 语句 
>
> **DCL**（Data Control Language），数据控制功能 用于执行权限授予和权限收回操作，主要是 GRANT , REVOKE 语句

#### select

> select语句，可以通过列名，把一行行的数据给查询出来

查看s_dept表中的所有记

```sql
select *
from s_dept;
```

查看s_dept表中所有记录的指定三个字段：id,name,region_id

```sql
select id,name,region_id
from s_dept;
```

#### 运算

```sql
select id,last_name,salary*12
from s_emp;
```

#### 别名

```sql
select old_column [as] new_column_name from tb_name;
```

#### 拼接

```sql
select col_name||'spe_char'||col_name from tb_name
```

#### nvl

> 可以替换数据中的null值

```sql
select nvl(col_name,change_value) from tb_name;
```

查看所有员工的员工id，名字和提成，如果提成为空，显示成0

```sql
select id,last_name,nvl(commission_pct,0) commission_pct
from s_emp;
```

#### distinct

该关键字可以将重复数据去除。

```sql
select distinct col_name,col_name...
from tb_name;
//distinct 只能在select后面。
后面有多行就是联合去重。
```

#### format

```sql
col last_name for a15;
```

#### sqlplus

> 使用 sqlplus 登录之后，可以使用buff（缓存）来存储/执行/修改上一条运行的sql语句 

- l 查看缓存中的sql语句
- a 在[定位]的那一行后面追加新的内容
- i 在[定位]的那一行下面插入新的一行
- c 替换[定位]的那一行中的某些字符串 ，格式为：c/老的字符串/新的字符串
- del 删除[定位]的那一行内容
- n 后面加内容可以重写这一行
- $ 后面跟一个终端命令，例如$cls清屏，linux中使用!
- / 执行缓存sql命令

如果要清空buff中的sql：**clear buffer**

#### 排序

```sql
select col_name,...
from tb_name
order by col_name [asc|desc]
```

默认为asc 可以不用写

#### 条件查询

```sql
select col_name,...
from tb_name
where col_name 比较操作表达式
```

**between and **两数之间

```sql
select id,last_name,salary
from s_emp
where salary between 700 and 1500;
```

**in()** ，表示值在一个指定的列表中

```sql
select id,last_name,salary
from s_emp
where id in (1,3,5,7,9);
```

**like** 模糊查询，在值不精确的时候使用

- % ，通配0到多个字符 
- _ ，通配一个字符，并且是一定要有一个字符 
- \ ，转义字符，需要使用 escape 关键字指定，转义字符只能转义后面的一个字符

```sql
select id,last_name,salary
from s_emp
where last_name like 'C%';
```

```sql
select id,last_name,salary
from s_emp
where last_name like '___n_%';
```

```sql
select id,last_name,salary
from s_emp
where last_name like '%\_%' escape '\';
```

**is null**  **is not null**判断值为null的时候使用，null值的判断不能使用等号

```sql
select id,last_name,commission_pct
from s_emp
where commission_pct is null;
```

**and 、 or** ，逻辑操作符，当条件有多个的时候可以使用

> and比or的优先级要高

## oracle（二）函数、多表查询、结果集、伪列

### 多表查询

> 多表查询，又称表联合查询，即一条sql语句涉及到的表有多张，表中的数据通过特定的连接，进 行联合显示
>

为了这种避免笛卡尔积的产生，在多表查询的时候，可以使用连接查询来解决这个问题。

连接查询又可以大致分为： 

1. 等值连接 
2. 不等值连接 
3. 外连接      左外连接 右外连接 全连接 
4. 自连接

#### 等值链接

利用一张表中某列的值，和另一张表中某列的值相等的关系，把俩张表连接起来，满足条件的数 据才会组合

#### 外连接

有时候两个表的数据不是一一对应的，用等值连接会漏查，所以要外连接

##### **左外连接**

```sql
select last_name,dept_id,name
from s_emp left outer join s_dept
on s_emp.dept_id=s_dept.id;
//简写
select last_name,dept_id,name
from s_emp,s_dept
where s_emp.dept_id=s_dept.id(+);
```

##### 右外连接

```sql
select last_name,dept_id,name
from s_emp right outer join s_dept
on s_emp.dept_id=s_dept.id;
//简写
select last_name,dept_id,name
from s_emp,s_dept
where s_emp.dept_id(+)=s_dept.id
```

##### 全连接

```sql
select last_name,dept_id,name
from s_emp full outer join s_dept
on s_emp.dept_id=s_dept.id;
//没有简写
```

##### 自连接

自连接就是一张表，自己和自己连接后进行查询

#### 操作结果集

- union ，取俩个结果集的并集 
- union all ，把俩个结果集合在一起显示出来 
- minus ，第一个结果集除去第二个结果集和它相同的部分 
- intersect ，求俩个结果集的交集

#### rownum（伪列）

Oracle中，有一个特殊的关键字rownum，被称为：伪列。 rownum只有Oracle数据中才有。

伪列并不能像表中真实的列一样随便操作，伪列只能用于查询

伪列，可以根据查询结果的条数，自动生成，并且一定是从1开始连续不断的数字 

伪列rownum的本质就是给查询的一行行结果标上行号























# JDBC

## jdbc（一）JUnit、JDBC、Batch、transaction

### JUnit的基础功能

```java
package com.briup.demo;
import org.junit.jupiter.api.AfterAll;
import org.junit.jupiter.api.AfterEach;
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.DisplayName;
import org.junit.jupiter.api.Test;
@DisplayName("junit测试用例")
public class JunitTest {
@BeforeAll
public static void init() {
System.out.println("初始化数据");
}
@AfterAll
public static void cleanUp() {
System.out.println("清理数据");
}
@BeforeEach
public void methoedStart() {
System.out.println("当前测试方法开始");
}
@AfterEach
public void methoedEnd() {
System.out.println("当前测试方法结束");
}
@DisplayName("测试1")
@Test
void test1() {
System.out.println(" 测试1执行");
}
@DisplayName("测试2")
@Test
void test2() {
System.out.println(" 测试2执行");
}
}
```

1. @DisplayName 用于标注测试类和测试方法的名字 

2. @Test 用于标注这个方法是测试方法 

3. @BeforeAll 在所有测试方法开始之前，执行一次（静态方法） 

4. @AfterAll 在所有测试方法结束之后，执行一次（静态方法） 

5. @BeforeEach 在每一个测试方法，执行开始之前，都会执行（非静态方法） 

6. @AfterEach 在每一个测试方法，执行结束之后，都会执行（非静态方法）

7. @RepeatedTest 重复测试

8. > @RepeatedTest 注解内，可以使用以下几个变量： currentRepetition ，表示已经重复的次数 totalRepetitions ，表示总共要重复的次数 displayName ，表示测试方法显示名称

9. @ValueSource  @ValueSource 配合 @ParameterizedTest 注解，可以表示当前测试方法，需要进行传参测试

```java
@DisplayName("测试2")
@RepeatedTest(3)
void test2() {
System.out.println(" 测试2执行");
}
```

```java
@DisplayName("测试2")
@RepeatedTest(value = 3, name = "{displayName} 第 {currentRepetition} 次")
void test2() {
System.out.println(" 测试2执行");
}

```

```java
@ParameterizedTest
@ValueSource(strings = {"tom","mary","poly"})
void test3(String name) {
System.out.println(" hello!"+name);
}
```

### JDBC

JDBC（Java DataBase Connectivity）Java数据库连接（技术），也就是能够通过java代码，连接到 数据库，并可以使用SQL语句，对数据库进行各种操作

**连接**

1. 加载驱动类 
2. 将驱动类注册到驱动管理器中（可以自动完成） 
3. 通过驱动管理器获取数据库连接对象

#### **加载驱动类的方式（三种）**

```java
@Test
public void test_driver1() {
String className = "oracle.jdbc.driver.OracleDriver";
try {
//forName方式加载驱动类
Class.forName(className);
} catch (ClassNotFoundException e) {
e.printStackTrace();
}
}
```

```java
@Test
public void test_driver2() {
//创建出驱动对象
Driver driver =
new oracle.jdbc.driver.OracleDriver();
}
```

```java
@Test
public void test_driver3() {
//设置环境变量
//jdbc.drivers=oracle.jdbc.driver.OracleDriver
//java -Djdbc.drivers=oracle.jdbc.driver.OracleDriver com.briup.test.Hello
//驱动管理器会自动加载该驱动类
System.setProperty("jdbc.drivers", "oracle.jdbc.driver.OracleDriver");
System.out.println(System.getProperty("jdbc.drivers"));
}
}
```

#### 获取链接

获取数据库连接对象，需要三个参数：

> - url，需要连接的数据库地址 
> - user，登录数据库的用户名 
> - password，登录数据库的密码



连接不同数据库的时候，url地址是不用的，如果是oracle数据库，则url地址如下：

```java
String url = "jdbc:oracle:thin:@127.0.0.1:1521:XE";
```

- thin 是oracle的一种连接方式 
- 后边必须有数据库所在主机的IP和PORT 
- XE表示连接的oracle数据库的名字 oralce数据库的名字，可以通过服务看到



java.sql.Connection 是JDBC中提供的一个接口，数据库连接对象必须是该接口的实现类对象 获取数据库连接对象的几种方式：

```java
public class ConnectionTest {
private String driverClass = "oracle.jdbc.driver.OracleDriver";
private String url = "jdbc:oracle:thin:@127.0.0.1:1521:XE";
private String user = "briup";
private String password = "briup";
//方式一
@Test
public void test_connection1() {
Connection conn = null;
try {
Class.forName(driverClass);

conn = DriverManager.getConnection(url,user,password);
System.out.println(conn);
} catch (ClassNotFoundException e) {
e.printStackTrace();
} catch (SQLException e) {
e.printStackTrace();
}finally {
if(conn!=null) {
try {
conn.close();
} catch (SQLException e) {
e.printStackTrace();
}
}
}
}
```

#### step

```java
Statement stmt = null;
stmt = conn.createStatement();
stmt.execute;
```

#### Batch

```java
//4.执行SQL语句
String sql1 = "drop table t_user";
String sql2 = "create table t_user("
+ "id number primary key,"
+ "name varchar2(50) not null,"
+ "age number"
+ ")";
String sql3 = "insert into t_user(id,name,age) values(1,'tom1',21)";
String sql4 = "insert into t_user(id,name,age) values(2,'tom2',22)";
String sql5 = "insert into t_user(id,name,age) values(3,'tom3',23)";
String sql6 = "update t_user set name='mary' where id>1";
//把要执行的sql语句，添加到批处理中
stmt.addBatch(sql1);
stmt.addBatch(sql2);
stmt.addBatch(sql3);
stmt.addBatch(sql4);
stmt.addBatch(sql5);
stmt.addBatch(sql6);
//执行批处理中的sql语句，返回每一个语句的结果
int[] rows = stmt.executeBatch();

```

#### Statement

> java.sql.Statement 接口，是专门用来执行sql语句的，该接口还有俩个子接口：

PreparedStatement

```JAVA
@Test
public void ps() {
Connection conn = null;
PreparedStatement ps = null;
try {
//1.加载注册驱动
Class.forName(driverClass);
//2.获取连接对象
conn = DriverManager.getConnection(url,user,password);
//3.获取PS对象
//具体每次不同的数据，可以先用占位符符表示，ps会提前把sql发给数据库预处理，后面
只发送数据
String sql = "insert into t_user(id,name,age)
values(user_seq.nextval,?,?)";
ps = conn.prepareStatement(sql);
//4.执行SQL语句
for(int i=1;i<=10000;i++) {
ps.setString(1, "tom"+i);
ps.setInt(2, 20);
ps.executeUpdate();
}
//5.处理结果
System.out.println("ps执行结束：");

```

 CallableStatement

用不到，没必要

## jdbc（二）连接池、封装、元数据

### 连接池

项目中 src下面，创建资源文件： druid.properties

```properties
driverClassName=oracle.jdbc.OracleDriver
url=jdbc:oracle:thin:@127.0.0.1:1521:XE
username=briup
password=briup
# 初始化连接数量
initialSize=5
# 最大连接数
maxActive=10
# 最大等待时间
maxWait=3000
```

```java
@Test
public void test_druid() {
Connection conn = null;
try {
Properties properties = new Properties();
InputStream is =
ConnectionTest.class.getClassLoader().getResourceAsStream("druid.properties");
properties.load(is);
//获取连接池对象
DataSource dataSource =
DruidDataSourceFactory.createDataSource(properties);
// 获取连接
conn = dataSource.getConnection();
System.out.println(conn);
} catch (Exception e) {
e.printStackTrace();
}finally {
if(conn!=null) {
try {
conn.close();
} catch (SQLException e) {
e.printStackTrace();
}
}

```

### 封装

```java
package com.briup.util;
import java.sql.Connection;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;
import javax.sql.DataSource;
import com.alibaba.druid.pool.DruidDataSourceFactory;
public class JdbcUtils {
private static DataSource dataSource;
static {
try {
Properties properties = new Properties();
properties.load(JdbcUtils.class.getClassLoader().getResourceAsStream("druid.prop
erties"));
dataSource = DruidDataSourceFactory.createDataSource(properties);
} catch (Exception e) {
e.printStackTrace();
}
}
public static Connection getConnection() throws SQLException {
return dataSource.getConnection();
}
public static void close(ResultSet rs,Statement stmt,Connection conn) {
if(rs!=null) {
try {
rs.close();
} catch (SQLException e) {
e.printStackTrace();
}
}
if(stmt!=null) {
try {
stmt.close();
} catch (SQLException e) {
e.printStackTrace();
}
}
if(conn!=null) {
try {
conn.close();
} catch (SQLException e) {
e.printStackTrace();
}
}
}
public static void close(Statement stmt,Connection conn) {
close(null,stmt,conn);
}
public static int executeUpdate(String sql) {
int rows = 0;
Connection conn = null;
Statement stmt = null;
try {
conn = getConnection();
stmt = conn.createStatement();
rows = stmt.executeUpdate(sql);
} catch (Exception e) {
e.printStackTrace();
} finally {
close(stmt,conn);
}
return rows;
}
}

```

# SpringMVC

## 创建SpringMVC步骤

1.创建一个web maven项目

2.导入依赖到pom.xml

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-webmvc</artifactId>
  <version>5.3.1</version>
</dependency>

<dependency>
  <groupId>javax.servlet</groupId>
  <artifactId>javax.servlet-api</artifactId>
  <scope>provided</scope> //导入tomcat之后就要加这一行，否则报错
  <version>3.1.0</version>
</dependency>


  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.tomcat.maven</groupId>
        <artifactId>tomcat7-maven-plugin</artifactId>
        <version>2.2</version>
        <configuration>
          <port>8080</port>
          <path></path>
        </configuration>
      </plugin>
    </plugins>
  </build>
```

3.配置spring配置文件

扫描范围内的spring注解

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:mvc="http://www.springframework.org/schema/mvc"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans-4.2.xsd
    http://www.springframework.org/schema/mvc
    http://www.springframework.org/schema/mvc/spring-mvc-4.2.xsd
    http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context-4.2.xsd">

    <context:component-scan base-package="com.wx.controller"/>

</beans>
```

4.配置web.xml文件

```xml
<!--配置前端控制器-->
<servlet>
  <servlet-name>springMVC</servlet-name>
  <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
  <!--初始化工作-->
  <init-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>classpath:springMVC.xml</param-value>
  </init-param>
</servlet>
<servlet-mapping>
  <servlet-name>springMVC</servlet-name>
  <url-pattern>/</url-pattern>
</servlet-mapping>
```

5.配置servlet类

```java
@Controller //当前类交给spring管理
```



```java
@RequestMapping("/test")//和配置servlet一样
```

```java
@RequestMapping("/hello")
public String Hello(){
    return "hello.jsp";     //直接返回web页面的名字，会直接跳转
}
```





```java
@RequestMapping("/helloMod")
public ModelAndView helloMod(){
    ModelAndView modelAndView=new ModelAndView();
    modelAndView.setViewName("hello.jsp");
    modelAndView.addObject("name","zs");    //将数据传到前端 前端页面用${}接收
    return modelAndView;
}
```



```java
@ResponseBody     //直接将string返回值传递到页面
@RequestMapping({"/susses","susses2"})//访问哪个都行，定义多个名字
public String test2(){
    return "susses";
}
```



```java
@RequestMapping(value = "postRequest",method = RequestMethod.POST)
public String PostRequest(){   //method设置请求方式是get还是post
    return "susses";
}
```



```java
@GetMapping("/get")//和@RequestMapping一样 直接设定好了是get请求
public String get(){
    return "get Susses";
}

@PostMapping("/get")//和@RequestMapping一样 直接设定好了是post请求
public String post(){
    return "get Susses";
}
```



```java
//通过servlet传参
@ResponseBody
@RequestMapping("req")
public String getParamByServlet(HttpServletRequest request){
    String name = request.getParameter("name");
    System.out.println(name);
    return name;
}                                     //获取页面传来的参数
//直接通过参数名获取
@ResponseBody
@RequestMapping("byName")
public String getParamByName(@RequestParam(value = "username",required = false) String name){//RequestParam起个名字  required 规定是否为必填 默认为true
    System.out.println("接受到名字"+name);
    return name;
}
```



```java
@GetMapping("/user")
@ResponseBody
    public String user(User user){ //传递对象直接传对象中的属性
    System.out.println(user);
        return "susses";
    }
```

# PodMan命令

```dockerfile
podman images   查看镜像
```

```
podman ps  运行中的镜像
```

```
podman exec -it mysql-test /bin/bash 进入mysqlrong'q
```

```
podman start 运行容器
```

# Linux命令

```shell
su 进入管理员账户
```

```shell
ifconfig 查看ip
```

```shell
 rm -f 删除单个文件
```

```shell
 tar zxvf 解压缩
```

```shell
二、对于centos7系统

centos7使用firewall命令来开启和关闭防火墙。

1.systemctl命令

（1）systemctl  status firewalld.service查看防火墙的状态；

（2）systemctl  start firewalld.service启动防火墙；

（3）systemctl  stop firewalld.service关闭防火墙；

（4）systemctl  restart firewalld.service重启防火墙；

（5）systemctl  enable firewalld.service开机启动防火墙；

（6）systemctl  disable firewalld.service开机禁用防火墙；

（7）systemctl  is-enabled firewalld.service查看防火墙是否开机启动；

```

```shell
./startup.sh

ps -ef | grep 'tomcat'

./catalina.sh run
```

```sh
ls 查询文件 参数 -l 纵向排列文件 -a 显示隐藏文件 -h 和-s同时使用 更详细的显示文件大小
```

```sh
pwd 查看当前所在文件夹位置
```

```shell
mkdir 创建文件夹 -p 一次创建多个层级的目录
```















 