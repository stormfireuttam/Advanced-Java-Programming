## Strings, StringBuffer & StringBuilder

### A) Purpose

Strings receive special treatment in Java because they are used frequently in a program and hence efficiency is crucial.
The designers of Java decided to retain primitive types in an object-oriented language, instead of making everything an object to improve the performance of the language.

Primitives are stored in the **call stack**, which require **less storage** spaces and are **cheaper** to manipulate.
Objects are stored in the **program heap**, which require **complex** memory management and **more** storage spaces.

For performance reason, Java's String is designed to be in b/w a primitive and a class.

### B) Explanation

#### 1) String are Objects in Java

In Java, Strings are objects and not a primitive type.

In the example

```System.out.println("Welcome to Java World");``` 

The string "Welcome to Java World" is a **String constant** or **String literal** or **String object**.

#### 2) String Construction

1. *Using a String Literal*:
```
String str1 = "Hello";
```


2. *Using a String Object*:
```
String str2 = new String(str1);
```


3. *Using **new** Keyword*:
```
String str3 = new String("Hello");
```


4. Using + operator(Concatenation):
```
String str4 = str1 + str2;
```

*Note: Each time you create a String literal, the JVM checks string pool first.
If the string literl already exists in the pool a reference to the pool instance is returned else a new string object is created and is placed in the pool.
String objects are stored in a special memory area known as **String constant pool** inside the heap memory.*

#### 3) String Object and how they are stored:

![image](https://user-images.githubusercontent.com/40880896/119552923-b26c3480-bdb8-11eb-8331-9eaa685e36df.png)

#### 4) String Literal vs String Object

Java has provided a special mechanism for keeping the String literals - **string common pool** i.e. if two string literals have the same contents, they will share the same storage inside the common pool.

On the other hand, String objects crated via new operator and constructor are kept in the heap. Each string object in the heap has its own storage just like any other object.
There is no sharing of storage in heap even if two String objects have the same contents.

#### 5) String is immutable

Strings are designed to be immutable. That is, once a String is constructed, its contents cannot be modified. Otherwise, the other String references sharingthe same storage location will be affected by the change, which can be unpredictable and therefore is undesirable.

If the contents of a String have to be modified frequently, use the **StringBuffer** or **StringBuilder** class.

```
 public class ImmutableStringObjects {
    public static void main(String args[]) {
        String s1 = "iByte";  //Statement 1
        String s2 = s1;       //Statement 2
        s2 = s1.concat("Code's"); //Statement 3
        s2 = s2 + " JavaWorld";   /Statement 4
        System.out.println("s1 = " + s1);
        System.out.println("s2 = " + s2);
    }
 }
```
**Reference Variables**: s1 and s2

**String Objects/literals**: "iByte", "Code's", "iByteCode's", "Java World", "iByteCode'sJavaWorld"

![image](https://user-images.githubusercontent.com/40880896/119557844-560c1380-bdbe-11eb-9c9e-3315d32cf46e.png)

![image](https://user-images.githubusercontent.com/40880896/119558000-818efe00-bdbe-11eb-9b05-4eadceb894e2.png)

![image](https://user-images.githubusercontent.com/40880896/119558038-8f448380-bdbe-11eb-9d27-c78fd0a3bf78.png)

**Why Strings are Immutable:**

1. Don't provide mutator methods for any field
2. Make all fields final and private
3. Don't allow subclasses by declaring the class final itself
4. Return deep cloned objects with copied content for all mutable fields in class

*Note: Immutable objects are among the simplest and most robust kinds of classes you can possibly build. When you create immutable classes, entire categories of problems simply disappear.* 


#### String Function

*compareTo()* : Compares two strings lexicographically(dictionary order). 

Result is *negative integer* if this String object lexicographically *precedes* the argument string. 
Result is *positive integer* if this String object lexicographically *follows* the argument string.


### C) Understanding StringBuffer and StringBuilder

Java provides 2 classes to support mutable strings: StringBuffer and StringBuilder. A StringBuffer or StringBuilder object is just like an object stored in the heap and not shared, and therefore, can be modified with causing adverse side-effects to other objects.

*StringBuilder* is same as *StringBuffer* class, expect that StringBuilder is not synchonized for multi-thread operations.However for single thread program, SringBuilder, without the synchronization overhead is more efficient.

#### 1) String Buffer

StringBuffer class is used when we have to make a lot of modifications to our string. It is also thread safe i.e. multiple threads cannot access it simultaneously.

*String Buffer Constructos* :

- StringBuffer() : empty string buffer with room for 16 characters
- StringBuffer(int size) : empty string and takes an integer argument to set capacity of the buffer
- StringBuffer(String str) : allocates room for additional 16 characters and thus reduces the number of reallocations that takes place.
- Stringbuffer(charSequence ch[]) : string buffer that contains the same characters as the specified CharSequence.


*StringBuffer Functions* :

- append() : concatenate to the end
- insert(pos, str) : inserts one string into another
- reverse() : reverse the characters with a StringBuffer object
- replace() : replaces the string from specified start index to the end index.
- capacity() : returns current capacity of StringBuffer object.

#### 2) StringBuilder

It is not synchronized, i.e. it is not thread safe. Its because StringBuilder methods are not synchronised.

StringBuilder is API-compatible with the StringBuffer class, i.e. having the same set of constructors and methods, but with no guarantee of synchronization. It can be a drop-in replacement for StringBuffer under a single-thread environment.

It has the same set of constructors and methods as StringBuffer.

### D) StringTokenizer

The processing of text consists of parsing a formatted input string. Parsing is the division of text into a set of discrete parts or tokens, which in a certain sequence can convey a semantic meaning. 

The StringTokenizer class provides the first step in this parsing process often called the lexer(lexical analyzer) or scanner. It implements the Enumeration interface hence given an input string, you can enumerate the individual tokens contained in the StringTokenizer.

To use StringTokenizer, you specify an input string and a string that contains delimiter.

*StringTokenizer Constructors*

- StringTokenizer(String, String, boolean) : constructs a StringTokenizer on the specified String using the specified delimiter set.
```
If the flag is false, delimiter characters serve to separate tokens. For example, if string is "hello geeks"
and delimiter is " ", then tokens are "hello" and "geeks".

If the flag is true, delimiter characters are 
considered to be tokens. For example, if string is "hello
 geeks" and delimiter is " ", then tokens are "hello", " " 
and "geeks".
```
- StringTokenizer(String, String)
- StringTokenizer(String) : Constructs a StringTokenizer on the speicified String, using the default delimiter set.

*StringTokenizer Methods*

- countTokens() : returns total number of tokens present so that we can use nextToken() method before it gives an exception.
- hasMoreTokens(): if tokens are present for the StringTokenizer’s string. Those characters that are considered to be delimiters by the StringTokenizer object are changed to characters in the string delimiter. Then the next token to the current position in the string is returned.
- nextToken(): returns the next token from the given StringTokenizer.

*Note: StringTokenizer is a legacy class that is retained for compatibility reasons although its use is discouraged in new code. It is recommended that anyone seeking this functionality use the split() method of String or the regex package instead*
