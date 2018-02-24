## Hibernate
*************


#### 712. What is Hibernate framework?

Hibernate is a popular **Ob**ject **R**elational **M**apping (ORM)
framework of Java. It helps in mapping the Object Oriented Domain
model to Relational Database tables.

Hibernate is a free software distributed under GNU license.
Hibernate also provides implementation of Java Persistence API
(JPA).

In simple words, it is a framework to retrieve and store data from
database tables from Java.

#### 713. What is an Object Relational Mapping (ORM)?

**O**bject **R**elational **M**apping (ORM) is a programming technique to
map data from a relational database to Object oriented domain
model. This is the core of Hibernate framework.

In case of Java, most of the software is based on OOPS design. But
the data stored in Database is based on **R**elation **D**atabase
**M**anagement **S**ystem (RDBMS).

ORM helps in data retrieval in an Object Oriented way from an
RDBMS. It reduces the effort of developers in writing queries to
access and insert data.

#### 714. What is the purpose of Configuration Interface in Hibernate?

`Configuration` interface can be implemented in an application to
specify the properties and mapping documents for creating a
`SessionFactory` in Hibernate.

By default, a new instance of Configuration uses properties
mentioned in `hibernate.properties` file.

Configuration is mainly an initialization time object that loads the
properties in helps in creating `SessionFactory` with these properties.

In short, `Configuration` interface is used for configuring Hibernate
framework in an application.

#### 715. What is Object Relational Impedance Mismatch?

**O**bject **R**elational **I**mpedance **M**ismatch (ORIM) is also known as
paradigm mismatch. It means that Object model and Relational
model do not work well with each other.

Relational model or a RDBMS represents data in tabular format
like a spreadsheet. Object model or OOPS represents the data as an
inter-connected graph of objects.

Mixing these two models leads to various problems. The common
name for these issues is **O**bject **R**elational **I**mpedance **M**ismatch.

#### 716. What are the main problems of Object Relational Impedance Mismatch?

Object model and Relational models (RDBMS) have following
problems that are part of Object Relational Impedance Mismatch:
Granularity: Object model is more granular than Relational model.
There are more classes in object model than the corresponding
tables in relational model.

**Inheritance**: Object model supports inheritance. But Relational
model does not have any concept of inheritance.
Identity: Relational model has just one criteria for sameness of data.
It is based on primary key. In object model like Java we can have
equals as well as == for sameness of objects.

**Associations**: In Object model associations are uni-directional. In
RDBMS, there is a concept of foreign key for association. Also
multiplicity of a relationship is hard to judge by looking at object
model.

**Data navigation**: In Object model, you can move from one object to
another object for getting data. Egg. you can retrieve and Employee
object, then go to its department object and then get the employees
in the department object. In RDBMS, we try to minimize the SQL
calls, so we get all the data by using joins.

#### 717. What are the key characteristics of Hibernate?

Hibernate has following key characteristics:

**Object/Relational Mapping (ORM)**: Hibernate provides ORM
capabilities to developers. So then can write code in Object model
for connecting with data in Relational model.

**JPA Provider**: Hibernate provides an excellent implementation of
Java Persistence API (JPA) specification.

**Idiomatic persistence**: Hibernate provides persistence based on
natural Object-oriented idioms with full support for inheritance,
polymorphism, association, composition, and the Java collections
framework. It can work with any data for persistence.

**High Performance**: Hibernate provides high level of performance
supporting features like- lazy initialization, multiple fetching
strategies, optimistic locking etc. Hibernate does not need its own
database tables or fields. It can generate SQL at system
initialization to provide better performance at runtime.

**Scalability**: Hibernate works well in multi server clusters. It has
built in scalability support. It can work well for small projects as
well as for large business software.

**Reliable**: Hibernate very reliable and stable framework. This is the
reason for its worldwide acceptance and popularity among
developer community.

**Extensible**: Hibernate is quite generic in nature. It can be configured
and extended as per the use case of application.

#### 718. Can you tell us about the core interfaces of Hibernate framework?


#### 719. How will you map the columns of a DB table to the properties of a Java class in Hibernate?


#### 720. Does Hibernate make it mandatory for a mapping file to have .hbm.xml extension?


#### 721. What are the steps for creating a SessionFactory in Hibernate?


#### 722. Why do we use POJO in Hibernate?


#### 723. What is Hibernate Query Language (HQL)?


#### 724. How will you call a stored procedure in Hibernate?


#### 725. What is Criteria API in Hibernate?


#### 726. Why do we use HibernateTemplate?


#### 727. How can you see SQL code generated by Hibernate on console?


#### 728. What are the different types of collections supported by Hibernate?


#### 729. What is the difference between session.save() and session.saveOrUpdate() methods in Hibernate?


#### 730. What are the advantages of Hibernate framework over JDBC?


#### 731. How can we get statistics of a SessionFactory in Hibernate?


#### 732. What is the Transient state of an object in Hibernate?


#### 733. What is the Detached state of an object in Hibernate?


#### 734. What is the use of Dirty Checking in Hibernate?


#### 735. What is the purpose of Callback interface in Hibernate?


#### 736. What are the different ORM levels in Hibernate?


#### 737. What are the different ways to configure a Hibernate application?


#### 738. What is Query Cache in Hibernate?


#### 739. What are the different types of Association mappings supported by Hibernate?


#### 740. What are the different types of Unidirectional Association mappings in Hibernate?


#### 741. What is Unit of Work design pattern?


#### 742. In Hibernate, how can an object go in Detached state?


#### 743. How will you order the results returned by a Criteria in Hibernate?


#### 744. How does Example criterion work in Hibernate?


#### 745. How does Transaction management work in Hibernate?


#### 746. How can we mark an entity/collection as immutable in Hibernate?


#### 747. What are the different options to retrieve an object from database in Hibernate?


#### 748. How can we auto-generate primary key in Hibernate?


#### 749. How will you re-attach an object in Detached state in Hibernate?


#### 750. What is the first level of cache in Hibernate?


#### 751. What are the different second level caches available in Hibernate?752.Which is the default transaction factory in Hibernate?


#### 753. What are the options to disable second level cache in Hibernate?


#### 754. What are the different fetching strategies in Hibernate?


#### 755. What is the difference between Immediate fetching and Lazy collection fetching?


#### 756. What is ‘Extra lazy fetching’ in Hibernate?


#### 757. How can we check is a collection is initialized or not under Lazy Initialization strategy?


#### 758. What are the different strategies for cache mapping in Hibernate?


#### 759. What is the difference between a Set and a Bag in Hibernate?


#### 760. How can we monitor the performance of Hibernate in an application?


#### 761. How can we check if an Object is in Persistent, Detached or Transient state in Hibernate?


#### 762. What is ‘the inverse side of association’ in a mapping?


#### 763. What is ORM metadata?


#### 764. What is the difference between load() and get() method in Hibernate?


#### 765. When should we use get() method or load() method in Hibernate?


#### 766. What is a derived property in Hibernate?


#### 767. How can we use Named Query in Hibernate?


#### 768. What are the two locking strategies in Hibernate?


#### 769. What is the use of version number in Hibernate?


#### 770. What is the use of session.lock() method in Hibernate?


#### 771. What inheritance mapping strategies are supported by Hibernate?