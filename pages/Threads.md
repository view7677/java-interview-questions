## [Threads](./Thread.md)

******************

#### What is multi-threading?

#### What is a Thread? Thread vs Process? What constitues threads? Which parts are shared?

#### How do you define threads?

#### What is volatile keyword? How does it work internally?

#### What is AtomicXXX variable? How does it work internally?

#### Atomic variable vs volatile variable.

#### What is synchronization? How do you achieve it in multi-threaded environment?

#### How does thread synchronization occurs inside a monitor?

A Monitor defines a lock and condition variables for managing concurrent access to shared data. The monitor uses the lock to ensure that only a single thread is active in the monitor code at any time. A monitor allows only one thread to lock an object at once.

#### What levels of synchronization can you apply ?

Object level and class level. Object level locking is mechanism when you want to synchronize a non-static method or non-static code block such that only one thread will be able to execute the code block on given instance of the class. This should always be done to make instance level data thread safe.Class level locking prevents multiple threads to enter in synchronized block in any of all available instances on run-time.

#### What is the difference between Thread.sleep() and Object.wait()?

#### Why sleep is a static method on Thread class where as wait and notify are defined on Object?