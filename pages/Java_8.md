#
# [Java 8](pages/Java_8.md)
****************




#### 1. What are the new features released in Java 8?

_The new features released in Java 8 are_:

1. Lambda Expression
2. Stream API
3. Date and Time API
4. Functional Interface Interface
5. Default and static methods in Interfaces
6. Optional Base64 Encoding and Decoding,
7. Nashorn JavaScript Engine,
8. Collections API Enhancements
9. Concurrency API Enhancements
10. Fork/Join Framework Enhancements
11. Spliterator Internal Iteration Type
12. Annotations and Repeatable Annotations
13. Method Parameter Reflection JVM Parameter Changes


#### 2. What are the main benefits of new features introduced in Java 8?

1. It’s Faster
2. Performance Improvements in Common Data Structures
3. Garbage Collector Improvements
4. Fork/Join Speed Improvements
5. Fewer Lines of Code
6. Lambda Expressions
7. New Methods on Our Favorite Collections
8. Streams API
9. Easy to Parallelize

#### 3. What is a Lambda expression in Java 8?

A lambda is a code block which can be referenced and passed to another piece of code for future execution one or more times.



#### 4. What are the three main parts of a Lambda expression in Java?

Three main parts of a Lambda expression are:

1. **Parameter list**: A Lambda expression can have zero or more parameters. Parameter list is optional to Lambda.

1. **Lambda arrow operator**: “->” is known as Lambda arrow operator. It separates the list of parameters and the body of Lambda.

2. **Lambda expression body**: The piece of code that we want to execute is written in Lambda expression body.

E.g. In following example:

```java
Arrays.asList( "a", "b", "d" ).forEach( e -> System.out.println( e ) );
```

1. Parameter list = e
2. Arrow = ->
3. Body = System.out.println( e )

#### 5. What is the data type of a Lambda expression?

A Lambda expression fulfills the purpose of passing code as data.

_The data type of a Lambda expression is a Functional interface._

In most of the cases this is java.lang.Runnable interface.

#### 6. _=> What is the meaning of following lambda expression?



#### 7. Why did Oracle release a new version of Java like Java 8?


#### 8. What are the advantages of a lambda expression?


#### 9. What is a Functional interface in Java 8?

A **Functional interface** in Java is an interface that has exactly one abstract method.

It can have default methods with implementation. A default method is not abstract.

In Java 8, `java.lang.Runnable` and `java.util.concurrent.Callable` are two very popular Functional interfaces.

#### 10. What is a Single Abstract Method (SAM) interface in Java 8?

A Functional interface is also known as Single Abstract Method Interface, since it has exactly one abstract method.

The example interfaces are `Runnanle`,`Callable`, `Comparator` and `ActionListener` etc. Java 8 has introduced Lambda Expressions to instantiate the interface and access the single abstract method easily.


```java
@FunctionalInterface
public interface ITrade{
public boolean check(Trade t);
}
```

```java
ITrade newTradeChecker = (Trade t) -> t.getStatus().equals("NEW");

// Or we could omit the input ype setting:
ITrade newTradeChecker=(t) -> t.getStatus().equals("NEW");
```


#### 11. How can we define a Functional interface in Java 8?

To define a Functional interface in Java 8, we can create an Interface with exactly one abstract method.

Another way is to mark an Interface with annotation `@FunctionalInterface`. Even with the annotation we have to follow the rule of exactly one abstract method.

The only exception to this rule is that if we override `java.lang.Object` class’s method as an abstract method, then it does not count as an abstract method.

#### 12. Why do we need Functional interface in Java?

Functional Interfaces are mainly used in Lambda expressions, Method reference and constructor references.

In functional programming, code can be treated as data. For this purpose Lambda expressions are introduced. They can be used to pass a block of code to another method or object.

Functional Interface serves as a data type for Lambda expressions. Since a Functional interface contains only one abstract method, the implementation of that method becomes the code that gets passed as an argument to another method.

#### 13. Is it mandatory to use `@FunctionalInterface` annotation to define a Functional interface in Java 8?


#### 14. What are the differences between Collection and Stream API in Java 8?

Main differences between Collection and Stream API in Java 8 are:

1. **Version**: Collection API is in use since Java 1.2. Stream API is recent addition to Java in version 8.
2. **Usage**: Collection API is used for storing data in different kinds of data structures. Stream API is used for computation of data on a large set of Objects.
3. **Finite**: With Collection API we can store a finite number of elements in a data structure. With Stream API, we can handle streams of data that can contain infinite number of elements.
4. **Eager vs. Lazy**: Collection API constructs objects in an eager manner. Stream API creates objects in a lazy manner.
5. **Multiple consumption**: Most of the Collection APIs support iteration and consumption of elements multiple times. With Stream API we can consume or iterate elements only once.



#### 15. What are the main uses of Stream API in Java 8?

The Streams API gives you flexibility to query and manipulate data. This is a powerful tool. Building fluent queries for your data is interesting in a Big Data world, but is just as useful for common operations.

Example, You have a list of books and you want to get a list of unique authors for these books, in alphabetical order:



```java

public List<Author> getAllAuthorsAlphabetically(List<Book> books) {
List<Author> authors = new ArrayList<>();
for (Book book : books) {
Author author = book.getAuthor();
if (!authors.contains(author)) {
authors.add(author);
}
}
Collections.sort(authors, new Comparator<Author>() {
public int compare(Author o1, Author o2) {
return o1.getSurname().compareTo(o2.getSurname());
}
});
return authors;
}
```
In the code above, we first iterate through the list of books, adding the book’s author to the author list if it hasn’t seen it before; then we sort the authors alphabetically by surname. This is exactly the sort of operation that streams have been designed to solve elegantly:

```java
public List<Author> getAllAuthorsAlphabetically(List<Book> books) {
return books.stream()
.map(book -> book.getAuthor())
.distinct()
.sorted((o1, o2) -> o1.getSurname().compareTo(o2.getSurname()))
.collect(Collectors.toList());
}

```

Not only is this fewer lines of code, it’s arguably more descriptive—a developer coming to this code later can read it and understand that
1) it’s getting authors from the books,
2) it’s only interested in unique authors, and
3) the list that is returned is sorted by author surname. Combine the Streams API with other new features—method references and new methods on Comparator—and you get an even more succinct version:

```java

public List<Author> getAllAuthorsAlphabetically(List<Book> books) {
return books.stream()
.map(Book::getAuthor)
.distinct()
.sorted(Comparator.comparing(Author::getSurname))
.collect(Collectors.toList());
}
```
Here it’s even more obvious that the sorted method orders by the author’s surname.


#### 16. What are the differences between Intermediate and Terminal Operations in Java 8 Streams?

Terminal operations produces a non-stream, result such as primitive value, a collection or no value at all. Terminal operations are typically preceded by intermediate operations which return another Stream which allows operations to be connected in a form of a query.

Main differences between Intermediate and Terminal Stream operations are as follows:

1. **Evaluation**: Intermediate operations are not evaluated until we chain it with a Terminal Operation of Stream. Terminal Operations can be independently evaluated.
2. **Output**: The output of Intermediate Operations is another Stream. The output of Terminal Operations is not a Stream.
3. **Lazy**: Intermediate Operations are evaluated in lazy manner. Terminal Operations are evaluated in eager manner.
4. **Chaining**: We can chain multiple Intermediate Operations in a Stream. Terminal Operations cannot be chained multiple times.
5. **Multiple**: There can be multiple Intermediate operations in a Stream operation. There can be only one Terminal operation in Stream processing statement.

#### 17. What is a `Spliterator` in Java 8?

A `Spliterator` is a special type of `Iterator` to traverse and partition the elements of a source in Java. A source can be a collection, an IO channel or a generator function.

It basically splits a `Collection`, partitioning off some of its elements as another `Spliterator`. It can be usefull for parallel programming.

A `Spliterator` may traverse elements individually or sequentially in bulk.

```java
Collection<String> coll = new ArrayList<>(); // Lets say size = 10
Spliterator<String> spliterator = coll.spliterator(); // Gives us Spliterator
Spliterator<String> newPartition = spliterator.trySplit();
long size = spliterator.estimateSize(); // size = 5
long size2 = newPartition.estimateSize(); // size = 5
```

#### 18. What are the differences between Iterator and Spliterator in Java 8?

Main differences between Iterator and Spliterator are as follows:

1. Spliterator can be used with Streams in Java 8. Where as, Iterator is just used with Collection.
2. Spliterator uses Internal Iteration to iterate Streams. Iterator uses External Iteration to iterate Collections.
3. Spliterator can iterate Streams in Parallel as well as Sequential manner. Iterator only iterates in Sequential manner.
4. Spliterator can traverse elements individually as well as in bulk. Iterator only iterates elements individually.

#### 19. What is Type Inference in Java 8?

Type inference is a Java compiler's ability to look at each method invocation and corresponding declaration to determine the type argument (or arguments) that make the invocation applicable. The inference algorithm determines the types of the arguments and, if available, the type that the result is being assigned, or returned. Finally, the inference algorithm tries to find the most specific type that works with all of the arguments.

To illustrate this last point, in the following example, inference determines that the second argument being passed to the pick method is of type Serializable:

```java
static <T> T pick(T a1, T a2) { return a2; }
Serializable s = pick("d", new ArrayList<String>());
```

#### 20. Does Java 7 support Type Inference?

limited supprt

#### 21. How does Internal Iteration work in Java 8?

In an Iterator, the fundamental question is that which party controls the iteration. Is it Iterator or the Collection on which iterator runs.

When a Collection controls the iterator, then it is called External Iteration. When the Iterator controls the iteration then it is called Internal Iteration.

In case of Internal Iteration, the client hands over an operation to Iterator and the Iterator applies the operation to all the elements in aggregate.

Internal Iteration is easier to implement, since the Iterator does not have to store the state of the collection.

#### 22. What are the main differences between Internal and External Iterator?


External Iterators Definition(or Active Iterators) – With external iterators responsibility of iterating over the elements, and making sure that this iteration takes into account the total number of records, whether more records exist to be iterated and so on lies with the programmer.

A brief look at the evolution of external iterators in java
Lets look into some external iterators which we have been using as java language evolved over the years.

Starting with Enumerations, iterations then moved on to Iterators(remember iterator(), next() or hasNext() methods for iterators). Then came Java 5 and along with came the enhanced for-loop which made use of generics to make iteration a lot easier. Lets see an example of enhanced for-loop introduced in Java 5 which uses the Iterable interface (you might already be familiar with this one) –

Enhanced for-loop example (uses external iterator)

```java
import java.util.*;

public class ExternalIterator {
public static void main(String args[]){
List<String> namesList=Arrays.asList("Tom", "Dick", "Harry");
for(String name:namesList){
System.out.println(name);
}
}
}
```
However, though we are explicitly not invoking hasNext() or next() methods while iterating over the list above, still the underlying code which makes this iteration work uses these methods. This implies that the complexity behind these operations is hidden from the programmer but it still exists. And it still is an active iterator.

All the above ways – Enumerations, Iterators and enhanced for-loop seem the natural way of iterating right!! Well yes, but then managing the iterations still remains the programmer’s job. Well not anymore with the advent of Internal Iterators in Java 8.

Internal Iterators(or Passive Iterators) – Internal Iterators manage the iterations in the background. This leaves the programmer to just declaratively code what is meant to be done with the elements of the Collection, rather than managing the iteration and making sure that all the elements are processed one-by-one.

Lets see how simple it is to say print all elements in an ArrayList in Java 8 using an example of internal iterator based forEach loop –

Example of internal iteration based forEach loop in Java 8

```java
import java.util.*;

public class InternalIterator {
public static void main(String args[]){
List<String> namesList=Arrays.asList("Tom", "Dick", "Harry");
namesList.forEach(name -> System.out.println(name));//Internal Iteration
}
}
```
In the above code, we are just telling the forEach method what to do(i.e. print) with each String in the namesList list using a lambda expression( In case you are not familiar with lambda expressions you can read.

All the work of iterating over the list of names one by one and printing them is taken care of internally by the runtime, leaving us with just declaratively defining only what is to be done i.e. print the names.

#### 23. What are the main advantages of Internal Iterator over External Iterator in Java 8?


#### 24. What are the applications in which we should use Internal Iteration?


#### 25. What is the main disadvantage of Internal Iteration over External Iteration?


#### 26. Can we provide implementation of a method in a Java Interface?

Java 8 interface changes include static methods and default methods in interfaces. Prior to Java 8, we could have only method declarations in the interfaces. But from Java 8, we can have default methods and static methods in the interfaces.

#### 27. What is a Default Method in an Interface?

For creating a default method in java interface, we need to use “default” keyword with the method signature. For example,
```java
package com.journaldev.java8.defaultmethod;

public interface Interface1 {

void method1(String str);
default void log(String str){
System.out.println("I1 logging::"+str);
}
}
```

#### 28. Why do we need Default method in a Java 8 Interface?


#### 29. What is the purpose of a Static method in an Interface in Java 8?


#### 30. What are the core ideas behind the Date/Time API of Java 8?


#### 31. What are the advantages of new Date and Time API in Java 8 over old Date API?


#### 32. What are the main differences between legacy Date/Time API in Java and Date/Time API of Java 8?


#### 33. How can we get duration between two dates or time in Java 8?


#### 34. What is the new method family introduced in Java 8 for processing of Arrays on multi core machines?


#### 35. How does Java 8 solve Diamond problem of Multiple Inheritance?
interface tells what to do and not how to do.

interface A has method draw.

interface B also has method draw.

These are method decleration and not implementations.

If a class implements both A and B then it has to implement eat method it is not diamond problem because eat of A and B are same.


_Java 1.8_
Allows interface method to have body.

It will give compilation error in such case.

In such case diamond problem may occur to overcome this we use super keyword

Eg A.super.eat

#### 36. What are the differences between Predicate, Supplier and Consumer in Java 8?


#### 37. Is it possible to have default method definition in an interface without marking it with default keyword?


#### 38. Can we create a class that implements two Interfaces with default methods of same name and signature?


#### 39. How Java 8 supports Multiple Inheritance?
In Java 8, there is support for Multiple inheritance at interface level. Let us understand by an example.

In following example, we are creating two interfaces Person and Employee. A teacher is a Person as well as an employee. But class Teacher gives compilation error.

```java
interface Person {
    public default void printType()  {
        System.out.println("I am a Person.");
    }
}
interface Employee {
    public default void printType() {
        System.out.println("I am a Employee.");
    }
}
public class Teacher implements Person, Employee {
    public static void main(String args[]) {
        Teacher t = new Teacher();
        t.printType(); //Error
    }
}
```

when we try to execute above class, we get the error:

“Error:(20, 8) java: class `com.java8.util.Teacher` inherits unrelated defaults for printType() from types `com.java8.util.Person` and `com.java8.util.Employee`”

To resolve this we have to explicitly override the printType method in Teacher class and use @Override annotation.

```java
package com.java8.util;

interface Person {
    public default void printType()  {
        System.out.println("I am a Person.");
    }
}

interface Employee {
    public default void printType()  {
        System.out.println("I am a Employee.");
    }
}
public class Teacher implements Person,Employee {
    @Override
    public void printType() {
        System.out.println("I am a Teacher.");
    }
    public static void main(String args[]) {
        Teacher t = new Teacher();
        t.printType();
    }
}
```
Output :

`I am a Teacher.`



#### 40. Can we access a static method of an interface by using reference of the interface?


#### 41. How can you get the name of Parameter in Java by using reflection?


#### 42. What is Optional in Java 8?

Another new feature of Java 8 is the new Optional type. This type is a way of explicitly stating “I might have a value, or I might be null.” Which means an API can now be explicit about either returning values that might be null vs. values that will always be non-null, minimizing the chances of running into a NullPointerException.

What’s nice about Optional is the way you tell it to deal with nulls. For example, if we’re looking for a particular book in a list, the new findFirst() method returns an Optional, which tells us it’s not guaranteed to find a value. Given this optional value, we can then decide what to do if it’s null. If we wanted to throw a custom Exception, we can use orElseThrow:

```java
public Book findBookByTitle(List<Book> books, String title) {
Optional<Book> foundBook = books.stream()
.filter(book -> book.getTitle().equals(title))
.findFirst();
return foundBook.orElseThrow(() -> new BookNotFoundException("Did not find book with title " + title));
}
```

#### 43. What are the uses of Optional?


#### 44. Which method in Optional provides the fallback mechanism in case of null value?


#### 45. How can we get current time by using Date/Time API of Java 8?


#### 46. Is it possible to define a static method in an Interface?


#### 47. How can we analyze the dependencies in Java classes and packages?


#### 48. What are the new JVM arguments introduced by Java 8?


#### 49. What are the popular annotations introduced in Java 8?


#### 50. What is a StringJoiner in Java 8?


#### 51. What is the type of a Lambda expression in Java 8?


#### 52. What is the target type of a lambda expression ?


#### 53. What are the main differences between an interface with default method and an abstract class in Java 8?


