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
9. Concurrency APIEnhancements
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


#### 17. What is a Spliterator in Java 8?

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


#### 21. How does Internal Iteration work in Java 8?


#### 22. What are the main differences between Internal and External Iterator?


#### 23. What are the main advantages of Internal Iterator over External Iterator in Java 8?


#### 24. What are the applications in which we should use Internal Iteration?


#### 25. What is the main disadvantage of Internal Iteration over External Iteration?


#### 26. Can we provide implementation of a method in a Java Interface?


#### 27. What is a Default Method in an Interface?


#### 28. Why do we need Default method in a Java 8 Interface?


#### 29. What is the purpose of a Static method in an Interface in Java 8?


#### 30. What are the core ideas behind the Date/Time API of Java 8?


#### 31. What are the advantages of new Date and Time API in Java 8 over old Date API?


#### 32. What are the main differences between legacy Date/Time API in Java and Date/Time API of Java 8?


#### 33. How can we get duration between two dates or time in Java 8?


#### 34. What is the new method family introduced in Java 8 for processing of Arrays on multi core machines?


#### 35. How does Java 8 solve Diamond problem of Multiple Inheritance?


#### 36. What are the differences between Predicate, Supplier and Consumer in Java 8?


#### 37. Is it possible to have default method definition in an interface without marking it with default keyword?


#### 38. Can we create a class that implements two Interfaces with default methods of same name and signature?


#### 39. How Java 8 supports Multiple Inheritance?


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


