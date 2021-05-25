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
- We can write a new instance method in the subclass that has the same name but different signature form the one in superclass thus overloading it.
- We can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
- 
