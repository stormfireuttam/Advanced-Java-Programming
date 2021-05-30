# Inheritance

## Introduction

Inheritance is the process of acquiring the properties of one class by another. It allows us to build hierarchies of classes/interfaces. It is also called IS-A relationship b/w classes/interfaces involved in the hierarchy.

A subclass inherits all the members(fields, methods and nested classes) from its superclass. Constructors are not members, so they are not inherited by sunclasses, but the constructor of the superclass can be invoked from the subclass.

Except **jav.lang.Object**, which has no superclass, every class has one and only one direct superclass. In the absence of any other explicit superclass, every class is implicitly a subclass of Object.

In an inheritance hierarchy, the classes/interfaces at the top of the hierarchy will be more Generic classes and the classes at the bottom of the hierarchy will be more Specialized. The subclasses can specialize themselves in the following ways:

- By re-declaring the attributes present in super class(Field Hiding)
- By adding new attributes
- By re-defining the instance methods present in super class(Method Overriding)
- By re-defining the static methods present in super class(Method Hiding)
- By adding new methods

## Theory

### Inheritance and Access Modifiers

- A subclass inherits all of the public and protected members of its parent, irrespective of the package the subclass is in.
- If the subclass is in the same packageas its parent, it also inherits the default members of the parent.
- We can declare a field in the subclass with the same name as the one in the superclass, thus hiding it. We can access the super class variables by using the super keyword.
- We can write a new instance method in the subclass that has the same name but different signature from the one in superclass thus overloading it.
- We can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
- A *nested class* has access to all the private members of its enclosing class - both fields and methods. Therefore, a public or protected nested class inherited by a subclass has indirect access to all of the private members of the superclass.
- The *final methods or variables* used in superclass will be inherited. The final variables cann be hidden. The final methods cannot be overridden but they can be overloaded in sub class.

### Types of Inheritance

- Single Inheritance
- Multiple Inheritance (in Java supported using interfaces)
- Multilevel Inheritance
- Hierarchical Inheritance (one class is extended by multiple classes)
- Hybrid Inheritance

### Super Keyword

**super** keyword is used to access the variables/methods of the object of super class. 

```
  class Employee {
    int empId;
    String empName, designation;
    Employee() {
      System.out.println("Employee Constructor");
    }
    public void display() {
      System.out.println("Employee display method");
    }
  }
  class RegularEmployee extends Employee {
    int basic;
    RegularEmployee() {
      System.out.println("Regular Employee Constructor");
    }
    public void display() {
      System.out.println("Regular Employee display method");
    }
    public void abc() {
      display();
      super.display();
    }
    public static void main(String[] s) {
      RegularEmployee re = new RegularEmployee();
      re.abc();
    }
  }
```

**Output:**
```
Employee Constructor
Regular Employee Constructor
Regular Employee display method
Employee display method
```

*Note: Always the order of invocation of constructor is from base class to the subclass.*

If a subclass constructor invokes a constructor of its superclass, either explicitly or implicitly, there will be a whole chain of constructors called, all the way back to the constructor of java.lang.Object class. This is called constructor chaining.

### Instance of Operator

- It is used to compare an object to a specified type. You can use it to test if an object is an instance of a class, an instance of a subclass or an instance of a class that implements a particular interface.
- All objects by default are instance of java.lang.Object as every class implicitly extends java.lang.Object.
- null is not an instance of any class or interace.

```
class Parent {}
interface MyInterface {}
class Child extends Parent implements MyInterfface{}
class InstanceOfDemo {
  public static void main(String ars[]) {
    Parent obj1 = new Parent();
    Parent obj2 = new Child();
    System.out.println(obj1 instanceOf Parent));
    System.out.println(obj1 instanceOf Child));
    System.out.println(obj1 instanceOf MyInterface));
    System.out.println(obj2 instanceOf Parent));
    System.out.println(obj2 instanceOf Child));
    System.out.println(obj2 instanceOf MyInterface));
    System.out.println(obj2 instanceOf Object));
  }
}
```

**Output :**

```
true
false
false
true
true
true
true
```


### Classes and Interfaces

- A class can extend only one another class in Java.
- An interface can extend any number of interfaces in Java.
- A class can implement any number of interfaces in Java.
- An interface cannot extend or implement a class.

### Error Zone

The readability and re-usability of code can also be obtained by using Composition instead of Inheritance. Inheritance needs to be used only when their is an is-a relationship and whether that is-a relationship will be constant throughout the lifetime of the application.








