# Java Tricky Questions




#### 413. Is there any difference between `a = a + b` and `a += b` expressions?

When we add two integral variables e.g. variables of type byte, short, or int in Java, then they are first promoted to int type, and then addition happens.

The += operator implicitly casts the result of addition into the type of variable used to hold the result. 

#### What happens when you put return statement or System.exit () on try or catch block? Will finally block execute?

Finally block executes even if we put a return statement in the try block or catch block. But finally block does not execute if you call System.exit() from try or catch block.



#### 414. What does the expression `1.0 / 0.0` return? Will there be any compilation error?

Double class is the source of many tricky interview questions. You may know about the double primitive type and Double class. But while doing floating point arithmetic some people don't pay enough attention to Double.INFINITY, NaN, and -0.0. There are rules that govern the floating point arithmetic calculations involving Double.

The answer to this question is that `1.0 / 0.0` will compile successfully. And it **will not throw `ArithmeticException`**. It will just return `Double.INFINITY`.

#### 415. Can we use multiple main methods in multiple classes?

Yes. When we start an application in Java, we just mention the class name to be run to java command. The JVM looks for the main method only in the class whose name is passed to java command. Therefore, there is no conflict amongst the multiple classes having main method.

#### 416. Does Java allow you to override a private or static method?

The question is tricky but the answer is very simple. You cannot override a private or static method in Java. If we create a similar method with same return type and same method arguments in child class, then it will hide the superclass method. This is known as method hiding.

Also, you cannot override a private method in sub class because Private method is not visible even in a subclass. Therefore, what you can do is to create another private method with the same name in the child class.

So in both the cases, it is not method overriding. It is either method hiding or a new method.

#### 417. What happens when you put a key object in a HashMap that is already present?

It will replace the old mapping because HashMap doesn't allow duplicate keys. The same key will have same HashCode as previous key object. Due to same HashCode, it will be stored at the same position in the bucket.

#### 418. How can you make sure that N threads can access N resources without deadlock?

This question checks your knowledge of writing multi-threading code. If you have experience with deadlock and race conditions, you can easily answer this.

The answer is that by resource ordering you can prevent deadlock. If in our program we always acquire resources in a particular order and release resources in the reverse order, then we can prevent the deadlock.

So a thread waiting for same resource can not get into deadlock while the other thread is trying to get it and holding the resource required by first thread. If both of them release the resources in right order, one of them can acquire it to finish the work.

#### 419. How can you determine if JVM is 32-bit or 64-bit from Java Program?

We can find JVM bit size 32 bit or 64 bit by running java command
from the command prompt.

Or we can get it from Java program.
Sun has a Java System property to determine the bit size of the
JVM: 32 or 64:
sun.arch.data.model=32 // 32 bit JVM
sun.arch.data.model=64 // 64 bit JVM
We can use `System.getProperty("sun.arch.data.model")` to determine
if it is 32/64 bit from Java program.

#### 420. What is the right data type to represent Money (like Dollar/Pound) in Java?

To represent money you need decimal points in the numbers like $1.99.

BigDecimal class provides good methods to represent Money. Using `BigDecimal`, we can do the calculation with decimal points and correct rounding. But using BigDecimal is a little bit high on memory usage.

We can also use double with predefined precision. But calculation on double can give erroneous results.



#### 421. How can you do multiple inheritances in Java?

Java does support multiple inheritances of by allowing an interface to extend other interfaces. You can implement more than one interface. But you cannot extend multiple classes. So Java doesn't support multiple inheritances of implementation.

But in Java 8, the default method breaks the rule of multiple inheritances behavior.

#### 422. Is ++ operation thread-safe in Java?

No, ++ operator is not a thread safe operation. It involves multiple
instructions like- reading a value, incrementing it and storing it back
into memory. These instructions can overlap between multiple
threads. So it can cause issues in multi-threading.

#### 423. How can you access a non-static variable from the static context?

We cannot access a non-static variable from the static context in
Java. If you write a code like that, then you will get compile time
error. It is one of the most common problems for beginner Java
programmers, when they try to access instance variable inside the
main method in a class.

Since main method is static in Java, and instance variables are nonstatic,
we cannot access instance variable inside main. The solution
is to create an instance of the object and then access the instance
variables.

#### 424. Let say there is a method that throws NullPointerException in the superclass. Can we override it with a method that throws RuntimeException?

We can throw superclass of RuntimeException in an overridden
method, but we cannot do the same if it is a checked Exception.

#### 425. How can you mark an array volatile in Java?

We can mark an array volatile in Java. But it makes only the reference to array volatile, not the whole array.

If one thread changes the reference variable to point to another array, then it will provide a volatile guarantee. But if multiple threads are changing individual array elements, they won't be having same reference due to the reference itself being volatile.

#### 426. What is a thread local variable in Java?

Thread-local variable is a variable restricted to a specific thread. It
is like thread's own copy of variable that is not shared among
multiple threads.

Java provides `ThreadLocal` class to support thread-local variables.
To achieve thread-safety, you can use it. To avoid any memory leak,
it is always good to remove a thread-local variable, once its work
is done.

#### 427. What is the difference between `sleep()` and `wait()` methods in Java?

In Java, we use these methods to pause currently running thread. There is a simple difference between these.

`sleep()` is actually meant for short pause because it doesn't release lock.

`wait()` is meant for conditional wait and it can release a lock that can be acquired by another thread to change the condition on which it is waiting.

#### 428. Can you create an Immutable object that contains a mutable object?

In Java, it is possible to create an Immutable object that contains a
mutable object.

We should not share the reference of the mutable object, since it is
inside an immutable object. Instead, we can return a copy of it to
other methods.

#### 429. How can you convert an Array of bytes to String?

You can convert an Array of bytes to String object by using the String constructor that accepts byte[]. We need to make sure that right character encoding is used. Else we may get different results after conversion.

#### 430. What is difference between `CyclicBarrier` and `CountDownLatch` class?

`CyclicBarrier` and `CountDownLatch` classes were introduced from Java 5.

We can reuse `CyclicBarrier` even if it is broken, but we cannot reuse `CountDownLatch` in Java.


> A synchronization aid that allows a set of threads to all wait for each other to reach a common barrier point. CyclicBarriers are useful in programs involving a fixed sized party of threads that must occasionally wait for each other. The barrier is called cyclic because it can be re-used after the waiting threads are released.

>A CyclicBarrier supports an optional Runnable command that is run once per barrier point, after the last thread in the party arrives, but before any threads are released. This barrier action is useful for updating shared-state before any of the parties continue.

#### 431. What is the difference between StringBuffer and StringBuilder?



#### 432. Which class contains clone method? Cloneable or Object class?



#### 433. How will you take thread dump in Java?



#### 434. Can you cast an int variable into a byte variable? What happens if the value of int is larger than byte?



#### 435. In Java, can we store a double value in a long variable without explicitcasting?



#### 436. What will this return `5*0.1 == 0.5` ? `true` or `false`?



#### 437. Out of an int and Integer, which one takes more memory?



#### 438. Can we use String in the switch case statement in Java?



#### 439. Can we use multiple main methods in same class?



#### 440. When creating an abstract class, is it a good idea to call abstract methods inside its constructor?



#### 441. How can you do constructor chaining in Java?



#### 442. How can we find the memory usage of JVM from Java code?



#### 443. What is the difference between x == y and x.equals(y) expressions in Java?



#### 444. How can you guarantee that the garbage collection takes place?



#### 445. What is the relation between x.hashCode() method and x.equals(y) method of Object class?



#### 446. What is a compile time constant in Java?



#### 447. Explain the difference between fail-fast and fail-safe iterators? You have a character array and a String. Which one is more secure to store sensitive data (like password, date of birth, etc.)?



#### 449. Why do you use volatile keyword in Java?



#### 450. What is the difference between `poll()` and `remove()` methods of Queue in Java?



#### 451. Can you catch an exception thrown by another thread in Java?



#### 452. How do you decide which type of Inner Class – Static or Non-Static to use in Java?



#### 453. What are the different types of Classloaders in Java?454.What are the situations in which you choose HashSet or TreeSet?



#### 455. What is the use of method references in Java?



#### 456. Do you think Java Enums are more powerful than integer constants?



#### 457. Why do we use static initializers in Java?



#### 458. Your client is complaining that your code is throwing `NoClassDefFoundError` or NoSuchMethodError, even though you are able to compile your code without error and method exists in your code. What could be the reason behind this?



#### 459. How can you check if a String is a number by using regular expression?



#### 460. What is the difference between the expressions String s ="Temporary" and String s = new String("Temporary ")? Which one is better and more efficient?



#### 461. In Java, can two equal objects have the different hash code?



#### 462. How can we print an Array in Java?



#### 463. Is it ok to use random numbers in the implementation of hashcode() method in Java?



#### 464. Between two types of dependency injections, constructor injection and setter dependency injection, which one is better?



#### 465. What is the difference between DOM and SAX parser in Java?



#### 466. Between Enumeration and Iterator, which one has better performance in Java?



#### 467. What is the difference between pass by reference and pass by value?



#### 468. What are the different ways to sort a collection in Java?



#### 469. Why Collection interface doesn’t extend Cloneable and Serializable interfaces?



#### 470. What is the difference between a process and a thread in Java?



#### 471. What are the benefits of using an unordered array over an ordered array?



#### 472. Between HashSet and TreeSet collections in Java, which one is better?



#### 473. When does JVM call the finalize() method?



#### 474. When would you use Serial Garabage collector or Throughput Garbage collector in Java?



#### 475. In Java, if you set an object reference to null, will the Garbage Collector immediately free the memory held by that object?



#### 476. How can you make an Object eligible for Garbage collection in Java?



#### 477. When do you use Exception or Error in Java? What is the difference between these two?



#### 478. What is the advantage of PreparedStatement over Statement class in Java?



#### 479. In Java, what is the difference between throw and throws keywords?



#### 480. What happens to the Exception object after the exception handling is done?



#### 481. How do you find which client machine is sending request to your servlet in Java?



#### 482. What is the difference between a Cookie and a Session object in Java?



#### 483. Which protocol does Browser and Servlet use to communicate with each other? What is HTTP Tunneling?



#### 485. Why do we use JSP instead of Servlet in Java?486.Is empty ‘.java’ file name a valid source file name in Java?



#### 487. How do you implement Servlet Chaining in Java?



#### 488. Can you instantiate this class?



#### 489. Why Java does not support operator overloading?



#### 490. Why String class is Immutable or Final in Java?



#### 491. What is the difference between sendRedirect and forward methods?



#### 492. How do you fix your Serializable class, if it contains a member that is not serializable?



#### 493. What is the use of run time polymorphism in Java?



#### 494. What are the rules of method overloading and method overriding in Java?



#### 495. What is the difference between a class and an object in Java?



#### 496. Can we create an abstract class that extends another abstract class?



#### 497. Why do you use Upcasting or Downcasting in Java ?



#### 498. What is the reason to organize classes and interfaces in a package in Java?



#### 499. What is information hiding in Java?



#### 500. Why does Java provide default constructor?



#### 501. What is the difference between super and this keywords in Java?



#### 502. What is the advantage of using Unicode characters in Java?



#### 503. Can you override an overloaded method in Java?



#### 504. How can we change the heap size of a JVM?



#### 505. Why should you define a default constructor in Java?506.How will you make an Object Immutable in Java?



#### 507. How can you prevent SQL Injection in Java Code?



#### 508. Which two methods should be always implemented by HashMap key Object?



#### 509. Why an Object used as Key in HashMap should be Immutable?



#### 510. How can we share an object between multiple threads?



#### 511. How can you determine if your program has a deadlock?