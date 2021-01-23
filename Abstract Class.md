next →← prev
다음 -> <- 이전
Abstract class in Java
Java 추상클래스
A class which is declared with the abstract keyword is known as an abstract class in Java. It can have abstract and non-abstract methods (method with the body).
Before learning the Java abstract class, let's understand the abstraction in Java first.
추상 키워드로 선언된 클래스를 Java에서 추상 클래스라고 합니다. 추상적이고 추상적이지 않은 방법(몸으로 하는 방법)
Java 추상 클래스를 학습하기 전에 먼저 Java의 추상화를 이해하겠습니다.

Abstraction in Java
추상화
Abstraction is a process of hiding the implementation details and showing only functionality to the user.
추상화는 구현 세부 정보를 숨기고 사용자에게 기능만 표시하는 프로세스이다.
Another way, it shows only essential things to the user and hides the internal details, for example, sending SMS where you type the text and send the message. You don't know the internal processing about the message delivery.
다른 방법은 사용자에게 중요한 내용만 표시하고, 예를 들어 텍스트를 입력하고 메시지를 보내는 SMS 전송과 같은 내부 세부 정보를 숨기는 방법이다. 이때, 메시지 전달에 대한 내부 처리를 알 수 없는 점이 있다.
Abstraction lets you focus on what the object does instead of how it does it.
추상화를 사용하면 객체가 수행하는 방식 대신 객체가 수행하는 작업에 집중할 수 있습니다.
Ways to achieve Abstraction
추상화하는 방법들
There are two ways to achieve abstraction in java
Java에서 추상화를 하는 방법으로는 두 가지 방법이 있다.
	1. Abstract class (0 to 100%)
	추상화 클래스 (0%에서 100%)
	2. Interface (100%)
       인터페이스 (100%)
Abstract class in Java
Java 추상클래스
A class which is declared as abstract is known as an abstract class. It can have abstract and non-abstract methods. It needs to be extended and its method implemented. It cannot be instantiated.
추상으로 선언된 클래스를 추상 클래스라고 한다. 클래스는 추상적이고 추상적이지 않은 방법으로 사용할 수 있는데, 클래스가 확장되고 그 방법이 실행되어야 하는 조건이 있다. 추상 클래스는 인스턴스화 될 수 없다.
Points to Remember
기억해야할 점들
	• An abstract class must be declared with an abstract keyword.
	추상 클래스는 추상 키워드로 선언되어야 한다.
	• It can have abstract and non-abstract methods.
	추상적인 메소드, 그렇지 않은 메소드를 사용할 수 있다.
	• It cannot be instantiated.
	인스터스화 될 수 없다.
	• It can have constructors and static methods also.
	생성자와 정적인 메소드 역시 가질 수 있다.
	• It can have final methods which will force the subclass not to change the body of the method.
	하위 클래스가 바디 메서드의 본문을 변경하지 않도록 하는 최종 메서드를 사용할 수 있다.

Example of abstract class
추상 클래스의 예시

abstract class A{}  

Abstract Method in Java
Java 추상 메서드
A method which is declared as abstract and does not have implementation is known as an abstract method.
추상적으로 선언되고 구현이 없는 메소드를 추상 메서드라고 합니다.
Example of abstract method
추상 메서드 예시

abstract void printStatus();//no method body and abstract  

Example of Abstract class that has an abstract method
추상 메서드가 있는 추상 클래스의 예
In this example, Bike is an abstract class that contains only one abstract method run. Its implementation is provided by the Honda class.
아래 예시에서 자전거는 추상 메서드 실행 하나만 포함하는 추상 클래스이다. 그것은 Honda 클래스에 의해 구현된다.

```java
abstract class Bike{  
  abstract void run();  
}  
class Honda4 extends Bike{  
void run(){System.out.println("running safely");}  
public static void main(String args[]){  
 Bike obj = new Honda4();  
 obj.run();  
}  
}  
```

Test it Now

시행

running safely
안전하게 실행 중

Understanding the real scenario of Abstract class
추상 클래스의 실제 시나리오 이해
In this example, Shape is the abstract class, and its implementation is provided by the Rectangle and Circle classes.
아래의 예시에서 Shape는 추상 클래스이며, 구현은 Rectangle 및 Circle 클래스에서 이뤄진다.
Mostly, we don't know about the implementation class (which is hidden to the end user), and an object of the implementation class is provided by the factory method.
대부분, 우리는 (최종 사용자에게 숨겨져 있는) 구현 클래스에 대해 알지 못하며, 구현 클래스의 객체는 팩토리 메서드에 의해 제공됩니다.
A factory method is a method that returns the instance of the class. We will learn about the factory method later.
팩토리 메서드는 클래스의 인스턴스를 반환하는 메서드이다. 팩토리 메서드에 대해서는 나중에 배울 것이다.
In this example, if you create the instance of Rectangle class, draw() method of Rectangle class will be invoked.
아래의 예시에서, 직사각형 클래스의 인스턴스를 만들면, 직사각형 클래스의 () 그리기 메서드가 호출될 것이다.

File: TestAbstraction1.java
abstract class Shape{  
abstract void draw();  
}  
//In real scenario, implementation is provided by others i.e. unknown by end user  
class Rectangle extends Shape{  
void draw(){System.out.println("drawing rectangle");}  
}  
class Circle1 extends Shape{  
void draw(){System.out.println("drawing circle");}  
}  
//In real scenario, method is called by programmer or user  
class TestAbstraction1{  
public static void main(String args[]){  
Shape s=new Circle1();//In a real scenario, object is provided through method, e.g., getShape() method  
s.draw();  
}  
}  
Test it Now
시행
drawing circle
원 그리기

Another example of Abstract class in java
Java 추상 클래스의 다른 예시

File: TestBank.java
abstract class Bank{    
abstract int getRateOfInterest();    
}    
class SBI extends Bank{    
int getRateOfInterest(){return 7;}    
}    
class PNB extends Bank{    
int getRateOfInterest(){return 8;}    
}    
    
class TestBank{    
public static void main(String args[]){    
Bank b;  
b=new SBI();  
System.out.println("Rate of Interest is: "+b.getRateOfInterest()+" %");    
b=new PNB();  
System.out.println("Rate of Interest is: "+b.getRateOfInterest()+" %");    
}}    

Test it Now
시행
Rate of Interest is: 7 %
이익: 7%
Rate of Interest is: 8 %
이익: 8%

Abstract class having constructor, data member and methods
생성자, 데이터 멤버 및 메서드가 있는 추상 클래스
An abstract class can have a data member, abstract method, method body (non-abstract method), constructor, and even main() method.
추상 클래스는 데이터 멤버, 추상 메서드, 메서드 본문(비추상 메서드), 생성자 및 주() 메서드를 포함할 수 있다.

File: TestAbstraction2.java
//Example of an abstract class that has abstract and non-abstract methods  
 abstract class Bike{  
   Bike(){System.out.println("bike is created");}  
   abstract void run();  
   void changeGear(){System.out.println("gear changed");}  
 }  
//Creating a Child class which inherits Abstract class  
 class Honda extends Bike{  
 void run(){System.out.println("running safely..");}  
 }  
//Creating a Test class which calls abstract and non-abstract methods  
 class TestAbstraction2{  
 public static void main(String args[]){  
  Bike obj = new Honda();  
  obj.run();  
  obj.changeGear();  
 }  
}  

Test it Now
시행
       bike is created
       running safely..
       gear changed
자전거는 안전하게 다니도록 설계되었다. 기어가 변경되었다.

Rule: If there is an abstract method in a class, that class must be abstract.
규칙: 클래스에 추상 메서드가 있다면 해당 클래스는 추상적일 것이다.
class Bike12{  
abstract void run();  
}  

Test it Now
시행
compile time error

Rule: If you are extending an abstract class that has an abstract method, you must either provide the implementation of the method or make this class abstract.
규칙:

Another real scenario of abstract class
The abstract class can also be used to provide some implementation of the interface. In such case, the end user may not be forced to override all the methods of the interface.
Note: If you are beginner to java, learn interface first and skip this example.

```java
interface A{  
void a();  
void b();  
void c();  
void d();  
}  
  
abstract class B implements A{  
public void c(){System.out.println("I am c");}  
}  
  
class M extends B{  
public void a(){System.out.println("I am a");}  
public void b(){System.out.println("I am b");}  
public void d(){System.out.println("I am d");}  
}  
  
class Test5{  
public static void main(String args[]){  
A a=new M();  
a.a();  
a.b();  
a.c();  
a.d();  
}}
```  

Test it Now
시행
Output:I am a
       I am b
       I am c
       I am d
결과: 나는 a이다.
       나는 b이다.
       나는 c이다.
       나는 d이다.
Next TopicInterface in Java
다음 주제 Interface in Java

← prev next →
<-이전 다음 ->


 For Videos Join Our Youtube Channel: Join Now

Help Others, Please Share

출처: <https://www.javatpoint.com/abstract-class-in-java>
