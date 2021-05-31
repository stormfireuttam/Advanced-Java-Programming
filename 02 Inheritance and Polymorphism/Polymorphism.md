# Polymorphism

- Polymorphism means existence in multiple forms. In the context of OOPs it means subclasses of a class can define their own unique behaviors and yet share some of the same functionality of the parent class.
- By adding new methods in subclass having same name as the methods in super class but with different parameter list **Method Overloading**
- By re-defining the methods present in super class **Method Overriding**. The methods will have the same signature as the methods in super class.

## Method Overloading (Compile Time Polymorphism) 

Methods having same name but different parameters. The parameters can differ in:
- Number of Parameters
- Type of Parameters
- Order of Parameters

The compiler does not consider return type when differentiating methods. Static, Final, Abstract methods can be overloaded.
Method overloading can be done within the same class as well as in an inheritance hierarchy.

## Method Overriding

Rules:
- Signature of method in super and sub class should be same.
- Return type should be the same or a subtype of the return type declared in the original overridden method in the super class. This subtype is called a co-variant return type.
- Access level can be less restrictive than the overridden method's access level.
- Method declared final or static cannot be overridden but can be overloaded.
- Method declared abstract can be overridden.
- Constructors cannot be overridden.
- The overriding method can throw narrower or fewer exceptions than the overridden method.

## Method Hiding

If a subclass defines a static method with the same signature as a static method in the superclass, then the method in the subclass hides the one in the superclass.
The distinction between hiding a static method and overriding an instance method has impoertant applications.

## Types of Polymophism

Depending on the time at which the resolution of a method call will be decided. It can be classified as:
- **Static Polymorphism :** If the method binding b/w method call and method definition happens at compile time, it is called Static Polymorphism. It is also called Compile time polymorphism or static binding or early binding. 
Java supports Static Polymorphism using Method Overloading, Method hiding using static, final, private methods.
- **Dynamic Polymorphism :** If method binding b/w method call and method defintion happens at runtime. Only JVM decides which method is called at run-time this is called dynamic method dispatch.
Java supports Dynamic Polymorphism with method overriding using instance methods.

## Upcasting and Downcasting

- Upcasting is changing type by moving up the inheritance hierarchy. This is always safe because it's always true that a SubType IS-A SuperType.
- Downcasting is changing type by moving down the inheritance hierarchy. This is NOT always safe, because it's NOT always true that a SuperType IS-A SubType. Therefore, an explicit cast is required when downcasting.
- 
