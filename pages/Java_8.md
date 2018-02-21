## [Java 8](pages/Java_8.md)
****************




#### 1. What are the new features released in Java 8?

_The new features released in Java 8 are_: 

1. Lambda Expression, 
2. Stream API, 
3. Date and Time API, 
4. Functional Interface Interface 
5. Default Static Methods 
6. Optional Base64 Encoding and Decoding, 
7. Nashorn JavaScript Engine,
8. Collections API Enhancements 
9. Concurrency Enhancements 
10. Fork/Join Framework Enhancements 
11. Spliterator Internal Iteration Type 
12. Annotations and Repeatable Annotations 
13. Method Parameter Reflection JVM Parameter Changes


#### 2. What are the main benefits of new features introduced in Java 8?


#### 3. What is a Lambda expression in Java 8?


#### 4. What are the three main parts of a Lambda expression in Java?


#### 5. What is the data type of a Lambda expression?


#### 6. What is the meaning of following lambda expression?


#### 7. Why did Oracle release a new version of Java like Java 8?


#### 8. What are the advantages of a lambda expression?


#### 9. What is a Functional interface in Java 8?


#### 10. What is a Single Abstract Method (SAM) interface in Java 8?


#### 11. How can we define a Functional interface in Java 8?


#### 12. Why do we need Functional interface in Java?


#### 13. Is it mandatory to use @FunctionalInterface annotation to define a Functional interface in Java 8?


#### 14. What are the differences between Collection and Stream API in Java 8?


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


#### 18. What are the differences between Iterator and Spliterator in Java 8?


#### 19. What is Type Inference in Java 8?


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


