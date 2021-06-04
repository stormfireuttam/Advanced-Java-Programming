# Introduction

**Definition:** An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions.

**Three Categories of Exceptions:**
- **Checked Exceptions:** It is typically a user error or a problem that cannot be foreseen by the programmer. These exceptions cannot be simply ignored at the time o compilation. For example, if a file is to be opened but the file cannot be found an exception occurs.
- **Runtime Exceptions:** It is an exception that occurs and probably could have been avoided by the programmer. As opposed to checked exceptions, runtime exceptions are ignored at the time of compilation.
- **Errors:**  These are not exceptions at all, but problems that arise beyond the control of the user or the programmer. Errors are typically ignored in your code because you can rarely do anything about an error. For example, if a stack overflow occurs, an error will arise. They are also ignored at the time of compilation. 

![image](https://user-images.githubusercontent.com/40880896/120783550-c77b5d00-c548-11eb-8258-db7a99b71791.png)

## Unchecked Exceptions

Not checked at compile time are called unchecked exceptions, classes that extends RuntimeException occurs under unchecked exceptions.

Some of the examples are:
- ArithmeticException (dividing a number from zero)
- ArrayIndexOutOfBoundsException (trying to access an index that does not exists)
- NullPointerException (trying to access a null object or performing operations on an object having a null value)
- ClassCastException
- IllegalStateException
- IndexOutOfBoundsException
- NegativeArraySizeException

## Checked Exceptions

Checked at compile-time. In Exception hierarchy all classes that extends Exception class except UnchekedException comes under checked exception category.

Some common CheckedExceptions in Java are:
- FileNotFoundException
- ParseException
- SQLException
- IOException

# Exception Handling in Java

### Using try-catch block in Java

![image](https://user-images.githubusercontent.com/40880896/120785674-f8f52800-c54a-11eb-921b-e9a72c03e225.png)

![image](https://user-images.githubusercontent.com/40880896/120785751-0dd1bb80-c54b-11eb-983a-00418ec1ef73.png)

## try 

A 'try' is the most commonly used keyword of Java Exception handling paradigm, a try block is one that is used to wrap th exception prone code inside it. 
If the exception occurs in try block then the control goes to catch block instantly. Every try block must have at least one catch or finally block with it, we will come to know about finally shortly.

## catch 

In the catch block we write code to deal with Exception conditions or some message or a stack trace of exception object to detect the exception reasons.
The advantage behind having more than one catch is that, sometimes we cannot predict which exception is going to be thrown at runtime, so we can provide a list of all expected exceptions in preceeding catch block.

## finally

A finally block is written followed by a try block or a catch block, code written inside a finally block is always executed.

## throws keyword

In Java if a code written within a method throws an exception, there can be two cases.
Either the code is being enclosed by try block and exception handling is implemented in the same method or the method can throw the exception to the calling method simply.
The 'throws' keyword throws the exception to immediate calling method in the hierarchy. The throws keyword appears at the end of a method's signature.

![image](https://user-images.githubusercontent.com/40880896/120791667-1c6fa100-c552-11eb-9cb4-01b3a06aae2b.png)

## throw keyword

In java it is possible to throw an exception programmatically, throws keyword is used to throw an exception explicitly. 

![image](https://user-images.githubusercontent.com/40880896/120792050-94d66200-c552-11eb-9ae1-629359e7b2ce.png)

