

## Method Overloading and Overriding
### 40. What is the other name of Method
Overloading?
Method Overloading is also known as Static Polymorphism.
### 41. How will you implement method overloading in Java?
In Java, a class can have multiple methods with same name but
different arguments. It is called Method Overloading. To implement
method overloading we have to create two methods with same name
in a class and do one/more of the following:
1.
2.
3.
Different number of parameters
Different data type of parameters
Different sequence of data type of parameters42. What kinds of argument
variations are allowed in Method
Overloading?
Method
in:
1.
2.
3.
Overloading allows two methods with same name to differ
Number of parameters
Data type of parameters
Sequence of data type of parameters
### 43. Why it is not possible to do
method overloading by changing
return type of method in java?
If we change the return type of overloaded methods then it will lead
to ambiguous behavior. How will clients know which method will
return what type. Due to this different return type are not allowed in
overloaded methods.
### 44. Is it allowed to overload main() method in Java?
Yes, Java allows users to create many methods with same name ‘main’. But only public static void main(String[] args) method is used for execution.
### 45. How do we implement method
overriding in Java?
To override a method, we just provide a new implementation of a
method with same name in subclass. So there will be at least two
implementations of the method with same name. One
implementation is in parent class. And another implementation is in
child class.
### 46. Are we allowed to override a static
method in Java?
No. Java does not allow overriding a static method. If you create a static method with same name in subclass, then it is a new method,
not an overridden method.
### 47. Why Java does not allow
overriding a static method?
To override a method, you need an instance of a class. Static method
is not associated with any instance of the class. So the concept of
overriding does not apply here.
Therefore, Java does not allow overriding a static method.48. Is it allowed to override an
overloaded method?
Yes. You can override an overloaded method in Java.
### 49. What is the difference between method overloading and method overriding in Java?
Differences between method overloading and overriding are:
1.
2.
3.
4.
Method overloading is static polymorphism. Method
overriding is runtime polymorphism.
Method overloading occurs within the same class. Method
overriding happens in two classes with hierarchy
relationship.
Parameters must be different in method overloading.
Parameters must be same in method overriding.
Method overloading is a compile time concept. Method
overriding is a runtime concept.
### 50. Does Java allow virtual functions?
Yes. All instance methods in Java are virtual functions by default.
Only class methods and private instance methods are not virtual
methods in Java.
###51. What is meant by covariant return
type in Java?
A covariant return type of a method is one that can be replaced by a
"narrower" type when the method is overridden in a subclass.
Let say class B is child of class A. There is a get() method in class
A as well as class B. get() method of class A can return an instance
of A, and get() method of class B return an instance of B. Here
class B overrides get() method, but the return type is different.
Before Java 5, any method that overrides the method of parent class
would have same return type.
From Java 5 onwards, a child class can override a method of parent
class and the child class method can return an object that is child of
object return by parent class method.Polymorphism
### 52. What is Runtime Polymorphism?
Runtime Polymorphism or Dynamic Polymorphism is the polymorphism that exists at runtime. In case of method overriding it
is not known which method will be called at runtime. Based on the
type of object, JVM decides the exact method that should be called.
So at compile time it is not known which method will be called at
run time.
### 53. Is it possible to achieve Runtime
Polymorphism by data members in
Java?
No. We need to create Runtime Polymorphism by implementing
methods at two levels of inheritance in Java.54. Explain the difference between
static and dynamic binding?
In Static binding references are resolved at compile time. In
Dynamic binding references are resolved at Run time.
E.g.
```java
Person p = new Person();
p.walk(); // Java compiler resolves this binding at compile time.
public void walk(Object o){
((Person) o).walk(); // this is dynamic binding.
}
```
## Abstraction
### 55. What is Abstraction in Object Oriented programming?
Abstraction is the process of hiding certain implementation details
of an object and showing only essential features of the object to
outside world.
It is different from Abstract class in Java.
Abstraction process identifies commonalities and hides the
complexity of implementation. It helps us in focusing on the
interface that we share with the outside world.
### 56. How is Abstraction different from Encapsulation?
Abstraction happens at class level design. It results in hiding the
implementation details. Encapsulation is also known as
“Information Hiding”. An example of encapsulation is marking the
member variables private and providing getter and setter for these
member variables.
### 57. What is an abstract class in Java?
An abstract class in Java has one or more abstract methods. An
abstract method is just declared in the abstract class, but it is not
implemented.
An abstract class has to be extended in Java and its abstract
methods have to be implemented by a child class. Also Java does
not allow new instance of Abstract class.
### 58. Is it allowed to mark a method abstract method without marking the class abstract?
No. Java specification says that if there is at least one abstract
method in a class, the class has to be marked abstract.
## 59. Is it allowed to mark a method abstract as well as final?
No. It will be contradictory statement to mark a method abstract as
well as final.
An abstract method has to be overridden by a child class. And a
final method cannot be overridden. Therefore a method can be
either abstract or final in Java.60. Can we instantiate an abstract
class in Java?
No. We cannot create an instance of an abstract class in Java.61. What is an interface in Java?
An Interface in Java is an abstract type blueprint of a class. It
contains the methods that a class must implement. It is like a
protocol.
It has method signatures and constant declarations.62. Is it allowed to mark an interface
method as static?
Yes, from Java 8 onwards, we can define static and default methods
in an interface. Prior to Java 8, it was not allowed.63. Why an Interface cannot be
marked as final in Java?
A final method cannot be overridden. But an interface method has to
be implemented by another class. So the interface method cannot be
marked as final.64. What is a marker interface?
There are interfaces that do not have any data member or methods.
These interfaces are called Marker interface.
E.g. Serializable, Cloneable, Remote etc.65. What can we use instead of
Marker interface?
We can use annotations instead of Marker interface.66. How Annotations are better than
Marker Interfaces?
Annotations serve the purpose of conveying metadata about the
class to its consumers without creating a separate type for it.
Annotations are more powerful than a Marker interface. They allow
programmers to pass more sophisticated information to classes that
"consume" it.67. What is the difference between
abstract class and interface in Java?
Differences between Abstract class and Interface are as follows:
1.
2.
3.
4.
An abstract class can have implemented methods with
body (non-abstract methods). Interface has only abstract
methods. From Java 8 onwards, interface can have
static/default methods in implemented form.
An abstract class can have instance member variables. An
interface cannot have instance variables. It can only have
constants.
An abstract class can have a constructor. Interface cannot
have constructor. It has to be implemented by another
class.
A class can extend only one abstract class. A class can
implement more than one interface.68. Does Java allow us to use private
and protected modifiers for variables
in interfaces?
No. All the variables in an interface are implicitly public.69. How can we cast to an object
reference to an interface reference?
An Object that implements an Interface can be cast to the same
Interface. Since An Object implementing an Interface already
provides implementation for the methods of that Interface, it is
allowed to do so as per the rules of Inheritance.Final70. How can you change the value of a
final variable in Java?
Java does not allow changing the value of a final variable. Once the
value is set, it cannot be changed.71. Can a class be marked final in
Java?
Yes a class can be marked final in Java. Once a class is marked
final, it cannot be extended.72. How can we create a final method
in Java?
To mark a method, add modifier final to that method. A final method
can not be overridden by a child class.73. How can we prohibit inheritance
in Java?
If you mark a class final, it cannot be extended. This will prohibit
the inheritance of that class in Java.74. Why Integer class in final in Java?
Integer class is a wrapper for int. If it is not marked final, then any
other class can extend it and modify the behavior of Integer
operations. To avoid this Integer wrapper class is marked as final.75. What is a blank final variable in
Java?
When we declare a final variable without giving any initial value,
then it is called blank final variable.76. How can we initialize a blank final
variable?
A blank final instance variable can be initialized in a constructor.
A blank final static variable can be initialized in the static block of
class.77. Is it allowed to declare main
method as final?
Yes, we can mark the main method as final.Package78. What is the purpose of package in
Java?
A package is used to encapsulate a group of classes, interfaces and
sub-packages. Often, it is a hierarchical structure of storing
information. It is easier to organize the related classes and sub-
packages in this manner.
A Package also provides access protection for classes and
interfaces. A package also helps in removing naming collision.79. What is java.lang package?
In Java, java.lang package contains the classes that are fundamental
to the design of Java programming language. The most important
class in this package is Object class.
It also contains wrapper classes like- Integer, Boolean, Character
etc. It provides Math class for mathematical operations.80. Which is the most important class
in Java?
It is an open-ended question with many answers. In my view, Object
class is the most important class of Java programming language. It
is the root of all the classes in Java. It provides some very
important and fundamental methods.81. Is it mandatory to import java.lang
package every time?
No. By default, JVM loads it internally.82. Can you import same package or
class twice in your class?
If we import same package multiple times in a class, compiler
includes it only once. So neither JVM nor Compiler gives any
error/warning on including a package multiple times.
If you have two classes with same name, then you may get name
collision on importing the class erroneously.
JVM internally loads the class only one time.83. What is a static import in Java?
Static import is similar to normal import declaration. Normal
import allows us to import classes from packages without using
package qualifier. Static import allows us to import static members
from a class without using class qualifier.84. What is the difference between
import static com.test.Fooclass and
import com.test.Fooclass?
First import is a static import and the second import is normal
import of a class. First import allows us to import static members of
class.Internationalization85. What is Locale in Java?
A Locale object represents a specific geographical, political, or
cultural region. It is used to locale-sensitive operations in Java.
It helps is following the local conventions of a country, native or
region. These conventions can be for formatting the dates, money,
numbers etc.86. How will you use a specific Locale
in Java?
To use a specific Locale, we need to load that Locale. We can use
ResourceBundle.getBundle("Locale.UK") method to load a Locale.Serialization87. What is the serialization?
Serialization is a process converting an object into a byte array.
This byte array represents the class, version and internal state of the
object. JVM can use this byte array to transmit/read the object over
a network.88. What is the purpose of
serialization?
Some of the uses of serialization are:
1.
2.
3.
4.
Communication: It is used for transmitting an object over
network between two machines.
Persistence: We can store the object’s state in a database
and retrieve it from database later on.
Caching: Serialization can be used for caching to improve
performance. We may need 10 minutes to build an object,
but it may take just 10 seconds to de-serialize the object.
Cross JVM Synchronization: It can be used in same way
across multiple JVM that follow different architecture.89. What is Deserialization?
Deserialization is the process of reconstructing the object from the
serialized state. It is the reverse process of serialization.90. What is Serialization and
Deserialization conceptually?
Serialization is to convert Object data into a stream of bytes
Deserialization is to convert a stream of bytes back into a copy of
the original object.91. Why do we mark a data member
transient?
Member variables of an object are marked transient to indicate that
they should not be serialized.
During serialization process the transient variables are not
considered part of the persistent state of an object.92. Is it allowed to mark a method as
transient?
No, Java does not allow marking a method as transient. The
transient keyword is valid only for member variables.93. How does marking a field as
transient makes it possible to serialize
an object?
Let say we have a class ABC that implements Serializable
interface, but it contains a member variable object of class XYZ
that does not implement Serializable interface. Due to this it is not
possible to Serialize the class ABC.
To solve this issue, we can mark the member variable XYZ as
Transient in class ABC. This will allow us to serialize the class
ABC.94. What is Externalizable interface
in Java?
Externalizable interface extends Serializable interface in Java. It is
used for giving the Class control over saving and restoring the
contents of its instances.
A class implements methods writeExternal() and readExternal() to
store and restore the object.95. What is the difference between
Serializable and Externalizable
interface?
Serializable is a marker interface but Externalizable is not a marker
interface.
When we implement Serializable interface, the class is serialized
automatically by default. We can override writeObject() and
readObject()methods to control more complex object Serialization
process.
In case of Externalizable, we use readExternal() and
writeExternal() methods to give control to class for class's
serialization process.
Serializable interface is based on recursive algorithm.
Serializable gives you two options. One option is to provide custom
way of serialization, the other default way. In Externalizable, you
have to always implement readExternal() and writeExternal()
methods.
A public no-arg constructor is needed while using Externalizable
interface.
In Serialization, we need to define serialVersionUID. If it is not
explicitly defined it will be generated automatically based on all the
fields, methods of the class.Reflection96. What is Reflection in Java?
Reflection is Java language's ability to inspect and dynamically call
classes, methods, attributes etc. at Runtime. It helps in examining or
modifying the Runtime behavior of a class at Runtime.97. What are the uses of Reflection in
Java?
Reflection is often used in Testing, Debugging and in Integrated
Development Environment (IDE).
Reflection allows you to write programs that do not have to "know"
everything at compile time. It makes programs more dynamic, since
they can be tied together at runtime.
Many modern frameworks like Spring etc. use Reflection. Some
modern languages like Python etc. also use Reflection.
JAVA API for XML Parsing (JAXP) also uses Reflection.98. How can we access private
method of a class from outside the
class?
We can use Reflection to access private method of a class from
outside the class. IN Java, we use getDeclaredMethod() to get
instance of a private method. Then we mark this method accessible
and finally invoke it.
In following sample code, we are accessing private method
message() of class Foo by Reflection.
FileName: Foo.java
public class Foo {
private void message(){System.out.println("hello java"); }
}
FileName: FooMethodCall.java
import java.lang.reflect.Method;
public class FooMethodCall{
public static void main(String[] args)throws Exception{
Class c = Class.forName("Foo");
Object o= c.newInstance();
Method m =c.getDeclaredMethod("message", null);
m.setAccessible(true);
m.invoke(o, null);
}
}99. How can we create an Object
dynamically at Runtime in Java?
We can use Reflection to create an Object dynamically at Runtime
in
Java.
We
can
use
Class.newInstance()
or
Constructor.newInstance() methods for creating such Objects.Garbage Collection100. What is Garbage Collection in
Java?
Java has an internal mechanism called Garbage collection to
reclaim the memory of unused projects at run time.
Garbage collection is also known as automatic memory
management.101. Why Java provides Garbage
Collector?
In Java, there are no pointers. Memory management and allocation
is done by JVM. Since memory allocation is automated, after some
time JVM may go low on memory. At that time, JVM has to free
memory from unused objects. To help with the process of
reclaiming memory, Java provides an automated process called
Garbage Collector.102. What is the purpose of gc() in
Java?
Java provides two methods System.gc() and Runtime.gc() to request
the JVM to run the garbage collection. By using these methods,
programmers can explicitly send request for Garbage Collection.
But JVM process can reject this request and wait for some time
before running the GC.103. How does Garbage Collection
work in Java?
Java has an automated process called Garbage Collector for
Memory Management. It is a daemon in JVM that monitors the
memory usage and performs memory cleanup. Once JVM is low on
memory, GC process finds the unused objects that are not
referenced by other objects. These unused objects are cleaned up by
Garbage Collector daemon in JVM.104. When does an object become
eligible for Garbage Collection in
Java?
An object can be Garbage Collected by JVM, if it is not reachable.
There are two cases for deciding eligibility of objects for Garbage
Collection:
1.
2.
An Object/instance that cannot be reached by a live thread.
A set of circularly referenced instances that cannot be
reached by any other instance outside that set.105. Why do we use finalize() method
in Java?
Java provides finalize() method to perform any cleanup before
Garbage Collection. This method is in Object class, and it is
invoked by JVM internally. Developers are free to implement this
method for any custom cleanup in case of Garbage Collection.
If an Object is not Garbage Collected, then this method may not be
called.
This method is never invoked more than once by JVM.106. What are the different types of
References in Java?
In Java, there are four types of references:
1.
2.
3.
4.
Strong Reference
Soft Reference
Weak Reference
Phantom Reference107. How can we reference an
unreferenced object again?
We can provide implementation in finalize() method to reference
and unreferenced object. For an unreferenced object, finalize()
method is called at the time of Garbage Collection. At this time,
Object can pass its reference ‘this’ to finalize() method and revive
itself.108. What kind of process is the
Garbage collector thread?
Garbage Collection is a Daemon process in JVM. It is an internal
process that keep checking Memory usage and cleans up the
memory.109. What is the purpose of the
Runtime class?
The purpose of the Runtime class is to provide access to the Java
Runtime system. This class provides certain important methods like:
1. Runtime.freeMemory() – This method returns the value of
free memory in JVM
2. Runtime.maxMemory() - This method returns the value of
maximum memory that JVM can use.
3. Runtime.gc() – This method can invoke garbage collection.110. How can we invoke an external
process in Java?
Java provides the method Runtime.getRuntime().exec() to invoke an
external process from JVM.111. What are the uses of Runtime
class?
Runtime class in Java provides following benefits:
1.
2.
3.
It allows to read data via key board
It can use system properties and environment variables
It helps in running non-java programs from within a java
application.Inner Classes112. What is a Nested class?
In Java, a Nested class is a class declared inside another class. We
can have more than one class declared inside a file.113. How many types of Nested classes
are in Java?
Java provides four types of Nested classes:
1.
2.
3.
4.
Member inner class
Local inner class
Anonymous inner class
Static nested class114. Why do we use Nested Classes?
There are following reasons for using nested classes:
1. Logical Grouping: We can logically group classes in one
place. If one class is useful to only one other class, then
we put smaller class within the larger class and keep them
in one file. This kind of nesting "helper classes" in a top-
level class makes the package more streamlined.
2. Encapsulation: Nested classes increase encapsulation. Let
say there are two top-level classes, Foo and Bar. Bar
needs access to private members of Foo. We can hide
class Bar within class Foo. In this way, private members
of Foo can be accessed by class Bar. So class Foo remains
encapsulated. Also, class Bar remains hidden from the
outside world.
3. Code Clarity: Nested classed make the code more
readable and well organized. Only Top-level classes are
exposed. The helper classes are kept hidden and closer the
code where it is used by a Top-level class.115. What is the difference between a
Nested class and an Inner class in
Java?
An Inner class in Java is non-static class. It is a type of Nested class
that is defined in another class but not qualified with a Static
modifier. A Nested class is also a class can be Static Nested class
or a non-Static Inner class.
An Inner class has access to other members of the enclosing class,
even if they are declared private. A Static Nested class can not
access the other members of the enclosing class.116. What is a Nested interface?
A Nested interface is declared inside another interface or a top-
level class. By default it is static.
A Nested interface is also known as Static interface.117. How can we access the non-final
local variable, inside a Local Inner
class?
Java allows a Local Inner class to access only Constant local
members. So we have to make the non-final local variable as final
constant to access it inside a Local Inner class.118. Can an Interface be defined in a
Class?
Yes, we can define a Static Nested interface within a class. Only the
enclosing class can access it.119. Do we have to explicitly mark a
Nested Interface public static?
A Nested Interface is implicitly public static. So the modifiers
public and static are redundant in declaration.120. Why do we use Static Nested
interface in Java?
Only the enclosing class can access a Static Nested interface.
Consider following code in which interface Xyz is enclosed in
class Abc.
public class Abc {
public interface Xyz {
void callback();
}
public static void registerCallback(Xyz xyz) {...}
}
// Client Code
Abc.registerCallback(new Abc.Xyz() {
public void callback() {...}
});
Any code that cannot access Abc can not access interface Xyz also.
So the purpose of declaring an Inner interface is to restrict its
access from outside world.String121. What is the meaning of
Immutable in the context of String
class in Java?
An Immutable object cannot be modified or changed in Java. String
is an Immutable class in Java.
Once a String object is created, it cannot be changed. When we
assign the String to a new value, a new object is created.122. Why a String object is considered
immutable in java?
Java language uses String for a variety of purposes. For this it has
marked String Immutable.
There is a concept of String literal in Java.
Let say there are 2 String variables A and B that reference to a
String object “TestData”. All these variables refer to same String
literal. If one reference variable A changes the value of the String
literal from “TestData” to “RealData”, then it will affect the other
variable as well. Due to which String is considered Immutable. In
this case, if one variable A changes the value to “RealData”, then a
new String literal with “RealData” is created and A will point to
new String literal. While B will keep pointing to “TestData”123. How many objects does following
code create?
Code:
String s1="HelloWorld";
String s2=" HelloWorld ";
String s3=" HelloWorld ";
The above code creates only one object. Since there is only one
String Literal “HelloWorld” created, all the references point to
same object.124. How many ways are there in
Java to create a String object?
Java provides two ways to create a String object. One is by using
String Literal, the other is by using new operator.125. How many objects does
following code create?
Code:
String s = new String("HelloWorld");
The above code creates two objects. One object is created in String
constant pool and the other is created on the heap in non-pool area.126. What is String interning?
String interning refers to the concept of using only one copy of a
distinct String value that is Immutable.
It provides the advantage of making String processing efficient in
Time as well as Space complexity. But it introduces extra time in
creation of String.127. Why Java uses String literal
concept?
Java uses String literal concept to make Java more efficient in
memory. If same String already exists in String constant pool, it can
be reused. This saves memory usage.128. What is the basic difference
between a String and StringBuffer
object?
String is an immutable object. Its value cannot change after creation.
StringBuffer is a mutable object. We can keep appending or
modifying the contents of a StringBuffer in Java.129. How will you create an immutable
class in Java?
In Java, we can declare a class final to make it immutable. There
are following detailed steps to make it Immutable:
1.
2.
3.
4.
5.
6.
Add final modifier to class to prevent it from getting
extended
Add private modifier to all the fields to prevent direct
access
Do not provide any setter methods for member variables
Add final modifier to all the mutable fields to assign value
only once
Use Deep Copy to initialize all the fields by a constructor
In clone method, return a copy of object instead of the
actual object reference130. What is the use of toString()
method in java ?
In Java, Object class has toString() method. This method can be
used to return the String representation of an Object. When we print
an object, Java implicitly calls toString() method.
Java provides a default implementation for toString() method. But
we can override this method to return the format that we want to
print.131. Arrange the three classes String,
StringBuffer and StringBuilder in the
order of efficiency for String
processing operations?
StringBuilder is the most efficient class. It does not have the
overhead of Synchronization. StringBuffer is a Synchronized class.
It has better performance than String but it is slower than
StringBuilder. String is the slowest for any String processing
operations, since it is leads to creation of new String literal with
each modification.
So the decreasing order of efficiency is: StringBuilder, StringBuffer,
StringException Handling132. What is Exception Handling in
Java?
Java provides Exception Handling mechanism to handle Runtime
errors that occur in JVM. There are checked exceptions in a
program that we expect to occur in certain situations.
Exception handling mechanism catches these checked exceptions
and takes relevant actions.133. In Java, what are the differences
between a Checked and Unchecked?
Checked Exceptions extend Throwable class, but they do not extend
RuntimeException or Error classes. UncheckedException extend
RuntimeException class.
Checked Exceptions are checked at compile time in Java.
Unchecked Exceptions happen at Runtime, so they are not checked
at compile time.
IOException, SQLException etc. are examples of Checked
Exceptions. NullPointerException, ArithmeticException etc. are
examples of Unchecked Exceptions.134. What is the base class for
Error and Exception classes in Java?
Error as well as Exception class is derived from Throwable class
in Java.135. What is a finally block in Java?
Java provides a finally block with a try block. This is an optional
block. But finally block is always executed after the execution of try
block.136. What is the use of finally block in
Java?
As per Java specification, a finally block is always executed,
whether an error occurs or not, whether an exception is handled or
not. It helps in doing the cleanup like- Rollback Transaction, Close
Connection, Close a file etc.137. Can we create a finally block
without creating a catch block?
Yes. A finally block can follow a try block or catch block. So we
can defined a finally block just after a try block.138. Do we have to always put a catch
block after a try block?
Java does not enforce the rule to put a catch block after try block.
We can write catch block or finally block after a try block.
Any exception that we want to catch is mentioned in catch block.139. In what scenarios, a finally block
will not be executed?
There are two main scenarios in which finally block is not
executed:
1.
2.
Program exits by calling system.exit() call.
A fatal error causes JVM to crash.140. Can we re-throw an Exception
in Java?
Yes, Java allows to re-throw an Exception.141. What is the difference between
throw and throws in Java?
Java provides throw keyword to throw an exception from a method
or a static block. Java provides throws keyword to mention the
probable exception thrown by a method in its declaration.
We use throw to explicitly throw an exception. We used
throws to declare an exception in method definition.
We cannot propagate checked exceptions with throw only. But
checked exceptions can be propagated with throws keyword.
A throw call is followed by an instance. Class or Exception follows
a throws keyword.
Call to throw occurs within a method. throws is just used with
method signature.
We can throw only one exception at a time. But we can mention as
many exceptions in throws clause.142. What is the concept of
Exception Propagation?
In Exception Propagation, uncaught exceptions are propagated in the
call stack until stack becomes empty. This propagation is called
Exception Propagation.
Let say an exception propagates from one method to another method.
A() calls B(), which calls C(), which calls D(). And if D() throws
an exception, the exception will propagate from D to C to B to A,
unless one of the methods catches the exception.143. When we override a method in
a Child class, can we throw an
additional Exception that is not
thrown by the Parent class method?
Yes, Java allows us to throw additional Exception in a child class,
but the additional exception should be an unchecked exception
(RuntimeException).Java Collection144. What is the difference between
Collection and Collections
Framework in Java?
In Java, a Collection is an object that contains multiple elements of
same type in a single unit. These multiple elements can be accessed
through one Collection object.
In Java Collections Framework is a library that provides common
architecture for creating, updating and accessing different types of
collections. In Collections framework there are common methods
that are frequently used by developers for working on a Collection
object.145. What are the main benefits of
Collections Framework in Java?
Main benefits of Collections Framework in Java are as follows:
1. Reusability: Java Collections Framework provides
common classes and utility methods than can be used with
different types of collections. This promotes the reusability
of the code. A developer does not have to re-invent the
wheel by writing the same method again.
2. Quality: Using Java Collection Framework improves the
program quality, since the code is already tested and used
by thousands of developers.
3. Speed: Most of programmers report that their development
speed increased since they can focus on core logic and use
the generic collections provided by Java framework.
4. Maintenance: Since most of the Java Collections
framework code is open source and API documents is
widely available, it is easy to maintain the code written
with the help of Java Collections framework. One
developer can easily pick the code of previous developer.146. What is the root interface of
Collection hierarchy in Java?
The root interface of Collection hierarchy in Java is Collection
interface.
But the Collection interface extends Iterable interface. Due to this
some people consider Iterable interface as the root interface.
Iterable interface is present in java.lang package but Collection
interface is present in java.util package. Oracle Java API docs
mention that Collection interface is a member of the Java
Collections framework.
Whereas, Iterable interface is not stated as a part of Java
Collections framework in Java docs.
Due to this Collection interface is the root of Collections
Framework.147. What are the main differences
between Collection and Collections?
Main differences between Collection and Collections are as
follows:
1. Collection is an interface in Java. But Collections is a
class in Java.
2. Collection is a base interface. Collections is a utility class
in Java.
3. Collection defines methods that are used for data structures
that contain the objects. Collections defines the methods
that are used for operations like access, find etc. on a
Collection.148. What are the Thread-safe
classes in Java Collections
framework?
The Thread-safe classes in Java Collections framework are:
Stack
Properties
Vector
Hashtable
BlockingQueue
ConcurrentMap
ConcurrentNavigableMap149. How will you efficiently
remove elements while iterating a
Collection?
The right way to remove elements from a collection while iterating
is by using ListIterator.remove() method.
E.g.
ListIterator<Integer> iter = myList.iterator();
while(iter.hasNext()) {
itr.remove();
}
Some developers use following code to remove an element which is
incorrect:
Iterator<Integer> iter = myList.iterator();
while(iter.hasNext()) {
itr.remove();
}
By doing so we get ConcurrentModificationException.
An iterator is first created to traverse the list. But at the same time
the list is changed by remove() method.
In Java, it is not allowed for a thread to modify a collection while
another thread is iterating it. ListIterator provides the capability of
removing an object during traversal.150. How will you convert a List into
an array of integers like- int[]?
We can use ArrayUtils class in Apache Commons Lang library.
Sample code is:
int[]intArray
=
Integer[0]));
ArrayUtils.toPrimitive(myList.toArray(new
If we use List.toArray(), it will convert List to Integer[].
Another option is:
int[] intArray = new int[myList.size()];
for (int i=0; i < myList.size(); i++) {
intArray [i] = myList.get(i);
}151. How will you convert an array of
primitive integers int[] to a List
collection?
We can use ArrayUtils in Apache Commons Lang library for this
purpose.
Sample code is:
List intList = Arrays.asList(ArrayUtils.toObject(intArray));
The other option would be to use a for loop and explicitly adding
integers to a List.
Sample code is:
int[]intArray = {10,20,30};
List<Integer> intList = new ArrayList<Integer>();
for (int i: intArray) {
intList.add(i);
}152. How will you run a filter on a
Collection?
We can use CollectionUtils of Apache for this purpose. We will
have to create a Predicate that will define the condition for our
filter. Then we can apply this Predicate in filter() method.
Sample code is:
In this example we filter any names that are less than 5 characters
long.
List<String> namesList = asList( "Red", "Blue", "Green" );
List<String> shortNamesList = new ArrayList<String>();
shortNamesList.addAll( namesList );
CollectionUtils.filter( shortNamesList, new Predicate(){
public boolean evaluate( Object input ) {
return ((String) input).length() < 5;
}
} );
We can also use Google Guava library for this.
In Java 8, we can use Predicate to filter a Collection through
Stream.153. How will you convert a List to a
Set?
There are two ways to convert a List to a Set in Java.
Option 1: Use HashSet
Set<Integer> mySet = new HashSet<Integer>(myList);
In this case we put a list into a HashSet. Internally hashCode()
method is used to identify duplicate elements.
Option 2: Use TreeSet
In this case we use our own comparator to find duplicate objects.
Set<Integer> mySet = new TreeSet<Integer>(myComparator);
mySet.addAll(myList);154. How will you remove duplicate
elements from an ArrayList?
The trick in this question is to use a collection that does not allow
duplicate elements. So we use a Set for this purpose.
Option 1: Use Set
If ordering of elements is not important then we just put the elements
of ArrayList in a HashSet and then add them back to the ArrayList.
Sample Code is:
ArrayList myList = // ArrayList with duplicate elements
Set<Integer> mySet = new HashSet<Integer>(myList);
myList.clear();
myList.addAll(mySet);
Option 2: Use LinkedHashSet
If ordering of elements is important then we put the elements of
ArrayList in a LinkedHashSet and then add them back to the
ArrayList.
Sample Code is:
ArrayList myList = // ArrayList with duplicate elements
Set<Integer> mySet = new LinkedHashSet<Integer>(myList);
myList.clear();
myList.addAll(mySet);155. How can you maintain a
Collection with elements in Sorted
order?
In Java, there are many ways to maintain a Collection with elements
in sorted order.
Some collections like TreeSet store elements in the natural
ordering. In case of natural ordering we have to implement
Comparable interface for comparing the elements.
We can also maintain custom ordering by providing a custom
Comparator to a Collection.
Another option is to use the utility method Collections.sort() to sort
a List. This sorting gives nlog(n) order of performance. But if we
have to use this method multiple times then it will be costly on
performance.
Another option is to use a PriorityQueue that provides an ordered
queue. The main difference between PriorityQueue and
Collections.sort() is that PriorityQueue maintains a queue in Order
all the time, but we can only retrieve head element from queue. We
cannot access the elements of PriorityQueue in Random order.
We can use TreeSet to maintain sorted order of elements in
collection if there are no duplicate elements in collection.156. What are the differences between
the two data structures: a Vector and
an ArrayList?
An ArrayList is a newer class than a Vector. A Vector is considered a
legacy class in Java. The differences are:
1.
2.
Synchronization: Vector is synchronized, but the ArrayList
is not synchronized. So an ArrayList has faster operations
than a Vector.
Data Growth: Internally both an ArrayList and Vector use
an array to store data. When an ArrayList is almost full it
increases its size by 50% of the array size. Whereas a
Vector increases it by doubling the underlying array size.157. What are the differences between
Collection and Collections in Java?
Main differences between Collection and Collections are:
1.
2.
3.
Type: Collection is an interface in Java. Collections is a
class.
Features: Collection interface provides basic features of
data structure to List, Set and Queue interfaces.
Collections is a utility class to sort and synchronize
collection elements. It has polymorphic algorithms to
operate on collections.
Method Type: Most of the methods in Collection are at
instance level. Collections class has mainly static methods
that can work on an instance of Collection.158. In which scenario, LinkedList
is better than ArrayList in Java?
ArrayList is more popular than LinkedList in Java due to its ease of
use and random access to elements feature.
But LinkedList is better in the scenario when we do not need
random access to elements or there are a lot of insertion, deletion of
elements.159. What are the differences between
a List and Set collection in Java?
Main differences between a List and a Set are:
1. Order: List collection is an ordered sequence of elements.
A Set is just a distinct collection of elements that is
unordered.
2. Positional Access: When we use a List, we can specify
where exactly we want to insert an element. In a Set there
is no order, so we can insert element anywhere without
worrying about order.
3. Duplicate: In a List we can store duplicate elements. A Set
can hold only unique elements.160. What are the differences between
a HashSet and TreeSet collection in
Java?
Main differences between a HashSet and TreeSet are:
1. Ordering: In a HashSet elements are stored in a random
order. In a TreeSet, elements are stored according to
natural ordering.
2. Null Value Element: We can store null value object in a
HashSet. A TreeSet does not allow to add a null value
object.
3. Performance: HashSet performs basic operations like
add(), remove(), contains(), size() etc in a constant size
time. A TreeSet performs these operations at the order of
log(n) time.
4. Speed: A HashSet is better than a TreeSet in performance
for most of operations like add(), remove(), contains(),
size() etc .
5. Internal Structure: a HashMap in Java internally backs a
HashSet. A NavigableMap backs a TreeSet internally.
6. Features: A TreeSet has more features compared to a
HashSet. It has methods like pollFirst(), pollLast(), first(),
last(), ceiling(), lower() etc.
7. Element Comparison: A HashSet uses equals() method for
comparison. A TreeSet uses compareTo() method forcomparison to maintain ordering of elements.161. In Java, how will you decide when
to use a List, Set or a Map collection?
1.
2.
If we want a Collection that does not store duplicate
values, then we use a Set based collection.
If we want to frequently access elements operations based
on an index value then we use a List based collection. E.g.
ArrayList
3. If we want to maintain the insertion order of elements in a
collection then we use a List based collection.
4. For fast search operation based on a key, value pair, we
use a HashMap based collection.
5. If we want to maintain the elements in a sorted order, then
we use a TreeSet based collection.162. What are the differences between
a HashMap and a Hashtable in Java?
Main differences between a HashMap and a Hashtable are:
1. Synchronization: HashMap is not a synchronized
collection. If it is used in multi-thread environment, it may
not provide thread safety. A Hashtable is a synchronized
collection. Not more than one thread can access a
Hashtable at a given moment of time. The thread that
works on Hashtable acquires a lock on it and it makes
other threads wait till its work is completed.
2. Null values: A HashMap allows only one null key and any
number of null values. A Hashtable does not allow null
keys and null values.
3. Ordering: A HashMap implementation by LinkedHashMap
maintains the insertion order of elements. A TreeMap sorts
the mappings based on the ascending order of keys. On the
other hand, a Hashtable does not provide guarantee of any
kind of order of elements. It does not maintain the
mappings of key values in any specific order.
4. Legacy: Hashtable was not the initial part of collection
framework in Java. It has been made a collection
framework member, after being retrofitted to implement the
Map interface. A HashMap implements Map interface and
is a part of collection framework since the beginning.
5. Iterator: The Iterator of HashMap is a fail-fast and it
throws ConcurrentModificationException if any other
Thread modifies the map by inserting or removing any
element except iterator’s own remove() method.Enumerator of the Hashtable is not fail-fast.163. What are the differences between
a HashMap and a TreeMap?
Main differences between a HashMap and a TreeMap in Java are:
1. Order: A HashMap does not maintain any order of its keys.
In a HashMap there is no guarantee that the element
inserted first will be retrieved first.
2. In a TreeMap elements are stored according to natural
ordering of elements. A TreeMap uses compareTo()
method to store elements in a natural order.
3. Internal Implementation: A HashMap uses Hashing
internally. A TreeMap internally uses Red-Black tree
implementation.
4. Parent Interfaces: A HashMap implements Map interface.
TreeMap implements NavigableMap interface.
5. Null values: A HashMap can store one null key and
multiple null values. A TreeMap can not contain null key
but it may contain multiple null values.
6. Performance: A HashMap gives constant time performance
for operations like get() and put(). A TreeMap gives order
of log(n) time performance for get() and put() methods.
7. Comparison: A HashMap uses equals() method to compare
keys. A TreeMap uses compareTo() method for
maintaining natural ordering.8.
Features: A TreeMap has more features than a HashMap. It
has methods like pollFirstEntry() , pollLastEntry() ,
tailMap() , firstKey() , lastKey() etc. that are not provided
by a HashMap.164. What are the differences
between Comparable and
Comparator?
Main differences between Comparable and Comparator are:
1. Type: Comparable<T> is an interface in Java where T is
the type of objects that this object may be compared to.
2. Comparator<T> is also an interface where T is the type of
objects that may be compared by this comparator.
3. Sorting: In Comparable, we can only create one sort
sequence. In Comparator we can create multiple sort
sequences.
4. Method Used: Comparator<T> interface in Java has
method public int compare (Object o1, Object o2) that
returns a negative integer, zero, or a positive integer when
the object o1 is less than, equal to, or greater than the
object o2. A Comparable<T> interface has method public
int compareTo(Object o) that returns a negative integer,
zero, or a positive integer when this object is less than,
equal to, or greater than the object o.
5. Objects for Comparison: The Comparator compares two
objects given to it as input. Comparable interface
compares "this" reference with the object given as input.
6. Package location: Comparable interface in Java is defined
in java.lang package. Comparator interface in Java is
defined in java.util package.165. In Java, what is the purpose of
Properties file?
A Properties file in Java is a list of key-value pairs that can be
parsed by java.util.Properties class.
Generally a Properties file has extension .properties e.g.
myapp.properties.
Properties files are used for many purposes in all kinds of Java
applications. Some of the uses are to store configuration, initial
data, application options etc.
When we change the value of a key in a properties file, there is no
need to recompile the Java application. So it provides benefit of
changing values at runtime.166. What is the reason for overriding
equals() method?
The equals() method in Object class is used to check whether two
objects are same or not. If we want a custom implementation we can
override this method.
For example, a Person class has first name, last name and age. If we
want two Person objects to be equal based on name and age, then
we can override equals() method to compare the first name, last
name and age of Person objects.
Generally in HashMap implementation, if we want to use an object
as key, then we override equals() method.167. How does hashCode() method
work in Java?
Object class in Java has hashCode() method. This method returns a
hash code value, which is an integer.
The hashCode() is a native method and its implementation is not
pure Java.
Java doesn't generate hashCode(). However, Object generates a
HashCode based on the memory address of the instance of the
object.
If two objects are same then their hashCode() is also same.168. Is it a good idea to use Generics
in collections?
Yes. A collection is a group of elements put together in an order or
based on a property. Often the type of element can vary. But the
properties and behavior of a Collection remains same. Therefore it
is good to create a Collection with Generics so that it is type-safe
and it can be used with wide variety of element