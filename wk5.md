### Polymorphism, what method gets called at runtime

- an object can be of multiple types simultaneously and methods to be called are based on object’s actual type at runtime.

### Compile and runtime

simple example: You want to write letter to your friend

Compile would be like grammarly. It checks for grammar/syntax errors.

Runtime → your friend actually reads your letter. In OOP context the code actually runs.

### Case 1: parent has the method, child has another method. the child method is called.

```java
public class Animal {
    void makeSound(){
        System.out.println("random sound");
    }
}
public class Dog extends Animal{
    void makeSound(){
        System.out.println("bark");
    }
}
class HelloWorld {
    public static void main(String[] args) {

        Animal myAnimal = new Dog();
        myAnimal.makeSound();
    }
}
```

output: bark.

- compile type is Animal. since Animal has makeSound();, no compile error.
- On runtime (when code actually runs), it runs the method from childclass

### Case 2: parent doesn’t have the method, child has some method. compile error

compile error: The method makeSound() is undefined for the type AnimalJava(67108964)

```java
public class Animal {
   
}
public class Dog extends Animal{
    void makeSound(){
        System.out.println("bark");
    }
}
class HelloWorld {
    public static void main(String[] args) {

        Animal myAnimal = new Dog();
        myAnimal.makeSound();
    }
}
```

### Question: Whats going on here?
```java
class Bike extends Vehicle{
    @Override
    void startEngine(){
        System.out.println("Bike engine started");
    }
}


class Car extends Vehicle{
    @Override
    void startEngine(){
        System.out.println("Car engine started");
    }
    void honk(){
        System.out.println("Car honking");
    }
}
class HelloWorld {
    public static void main(String[] args) {

        Vehicle myCar = new Car();
        Vehicle myBike = new Bike();
        myCar = (Car) myCar;

        myCar.startEngine();
        myBike.stopEngine();
        myCar.stopEngine();
        myCar.honk();
    }
}
```
from my understanding, doing myCar = (Car) myCar; changes myCar's compile type from Vehicle to Car. If that is the case, why does the program fail to compile because the honk() method is not defined in the Vehicle class?

### Query 2: Qn 10 of the quiz.

I chose b, was wondering why that is wrong? thank you!
```java
class HelloWorld {
    public static void main(String[] args) {

        String a = "hello";
        boolean equality = a.equals(a);
System.out.println(equality); // true
    }
}
```
