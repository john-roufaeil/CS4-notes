# CS4-notes
Notes for CS4 game course 

> Please consider contributing

## Final modifier

If you won't a method to be overridden.
``` java
public final void doSomething(){

}
```

If you don't want a class to be inherited, you can use the final
modifier too.

```java
public final class Hello{
    ...
}
```

## Refrence type vs Object type
   refrence type is the type written before equal and object type is the type we call constructor from it
```java 
public class A {
    char x = 'A';
    public void run {
        System.out.println("Object type is  A");
    }
}
```
```java
public class B extends A {
    char x = 'B'
    public void run {
        System.out.println("Object type is B");
    }
}
```

what would be result of?

```java
A a = new A ();
B b = new B ();
A trick = new B();
```

```java
System.out.println(a.x);
System.out.println(b.x);
System.out.println(trick.x);

System.out.println("------");

a.run();
b.run();
trick.run();
```
Results are 
```
A
B
A
------
Object type is A
Object type is B
Object type is B
```
`conclusion` late binding does not apply to instance variable but apply to instance methods 

## Type Casting 
```java 
public class Animal (){
    public void run (){
        System.out.println ("can have 2 or 4 legs")
    }
}
```
```java
public class FourLegsAnimal extends Animal (){
    public void run (){
        System.out.println("actually has 4 legs");
    }
}
```
```java 
public class Dog () extends FourLegsAnimal{
    public void run (){
        System.out.println("It's a dog");
    }
}
```
what would be the output of 
```java
Animal d = new Dog ();
d.run();
((Animal) d).run();
((FourLegsAnimal) d).run();
```
Output is 
It's a dog

It's a dog 

It's a dog 

`conclusion` type cast does not affect method calls (it will be called from object type class) 

What about 
```java
Animal a = new FourLegsAnimal();
((Dog) a).run();
```
it will give a run time error cannot cast from FourLegsAnimal to Dog 
`Note` you can not type cast to lower class (sub class) (`important` lower Class means lower class of object type). 

## Multiple Inheritance
You can extend (only one class) and then implement (any number of interfaces). Respectively. *Java doesn't have multiple inheritance*

