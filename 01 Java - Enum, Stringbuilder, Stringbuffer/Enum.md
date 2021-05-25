## What is Enumeration

**Enums** are lists of constants. When you need a predefined list of values which do not represent some kind of numeric or textual data, you use an enum.

![image](https://user-images.githubusercontent.com/40880896/119546465-931dd900-bdb1-11eb-8a61-fdd574aa7fd6.png)

Basic Enum declaration looks like
```
  access-modifier enum enum-name
  {
      enum_1,
      enum_2     //optional semi colon
  }
```
Enum keyword represents a special data type that enables for a variable to belong to a set of predefined constants. The values are implicitly **final** and **static**.

The enum can be defined within or outside the class because it is similar to a class.

![image](https://user-images.githubusercontent.com/40880896/119547914-4e933d00-bdb3-11eb-92b4-9cc2011d9a8c.png)

![image](https://user-images.githubusercontent.com/40880896/119548229-9ca84080-bdb3-11eb-8051-ea961f04172e.png)

### Advantages of Enum

![image](https://user-images.githubusercontent.com/40880896/119546678-ceb8a300-bdb1-11eb-9791-dcf4f375d07e.png)

### Constructor for an Enum 

![image](https://user-images.githubusercontent.com/40880896/119547094-4d154500-bdb2-11eb-9dfc-cddc2605cd4c.png)

### Enum Functions

Using **valueOf()**
  returns enum constant for a specified enum type, specified name
  
### Enum in Java are reference type

Like class or interface you can define constructor, methods and variables inside java Enum which makes it more powerful than enum in C and C++

### Specifying values of Enum Constants

![image](https://user-images.githubusercontent.com/40880896/119548809-3b34a180-bdb4-11eb-94ca-aa5a909c089d.png)

### Sample Code

![image](https://user-images.githubusercontent.com/40880896/119549285-b1390880-bdb4-11eb-813c-e22c095236e9.png)
