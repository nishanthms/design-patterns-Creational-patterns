
# Creational Design Patterns

### Table of Contents

- [Introduction](#introduction)
- [Singleton Pattern](singleton-pattern)
- Factory Method Pattern
- Abstract Factory Pattern
- Builder Pattern
- Prototype Pattern

## Introduction

Creational design patterns are patterns in software engineering that provide ways to create objects efficiently and flexibly, decoupling the object creation process from the rest of the application, improving modularity and flexibility.

Most commonly used creational design patterns:

- Singleton Pattern
- Factory Method Pattern
- Abstract Factory Pattern
- Builder Pattern
- Prototype Pattern


## Singleton Pattern

Singleton pattern is a creational design pattern that ensures that a class has only one instance, providing a global point of access to it.This pattern is useful when a single instance of a class is needed to coordinate actions within a system.

### When should we use this Pattern?

The Singleton pattern is appropriate when a single instance of a class needs to coordinate actions across a system, and when it is important to ensure that there is only one instance of the class in the system. Here are some situations where the Singleton pattern might be appropriate:

- When managing access to a shared resource such as a database connection, file system, or network socket.<br>
    Example: Suppose you are building a system that needs to manage access to a shared database connection. You want to ensure that there is only one instance of the database connection object in the system, and that this instance is accessible from all parts of the system. In this case, you might use the Singleton pattern to create a single instance of the database connection object that can be shared throughout the system

- When coordinating actions across the system, such as managing a system configuration or logging system.

- When there is a need for a single, global point of control, such as in a command or control system.

### Implementation

The Singleton pattern is implemented by defining a class with a private constructor and a static method that returns the instance of the class. Once the instance is created, the static method returns the same instance every time it is called.

### Code

TODO

### Examples

- Java Runtime Environment (JRE): The JRE uses the Singleton pattern to ensure that only one instance of the Runtime class is created in a running application. This is important because the Runtime class provides a number of system-wide resources and services, such as access to the command line arguments and the ability to execute system commands.

- Spring Framework: The Spring Framework, which is a popular framework for building enterprise applications in Java, uses the Singleton pattern extensively. For example, the ApplicationContext, which is the central interface for accessing the Spring container, is implemented as a Singleton.

- Logging frameworks: Many logging frameworks, such as Log4j, .NET (log4net and NLog) and Apache Commons Logging, use the Singleton pattern to ensure that only one instance of the logging object is created in a running application. This helps to prevent the logging framework from being overloaded with too many log requests.

- HttpContext in System.Web(ASP .NET): The HttpContext class in the System.Web namespace is used to provide access to the current HTTP request and response context in ASP.NET applications. It is also implemented as a Singleton, ensuring that there is only one instance of the HttpContext class per HTTP request

### Drawbacks

- Global state: The Singleton pattern can create global state, which can make it difficult to understand and test the behavior of a system. This can lead to bugs and inconsistencies.

- Thread-safety issues: If the Singleton class is not implemented properly, it can lead to thread-safety issues, such as race conditions and deadlocks.

- Difficulty with testing: Because the Singleton pattern creates a global state, it can be difficult to test the behavior of a system. It can also make it difficult to isolate and mock dependencies for unit testing.

- Complexity: The Singleton pattern can add complexity to a system by introducing a new design pattern. This can make it more difficult to understand and maintain the code.

- Violation of Single Responsibility Principle: If the Singleton class is overloaded with multiple responsibilities, it can violate the Single Responsibility Principle and make the class difficult to maintain.

- Difficulties with extension: It can be difficult to extend a system that uses the Singleton pattern because the Singleton class is a concrete class, and it is not designed to be extended.


### Best Practices

- Make the Singleton class sealed: To prevent any sub-classes from being created, it is a good practice to make the Singleton class sealed.

 - Use lazy initialization: The Singleton instance should not be created until it is first requested, and it should be created only once. Using lazy initialization ensures that the instance is created only when it is needed, and it is thread-safe.

- Implement thread-safety: The Singleton pattern is commonly used in multi-threaded applications, so it is important to ensure that the implementation is thread-safe. This can be achieved using locks or other thread-safety mechanisms, such as the Lazy<T> type in .NET.

- Avoid global state: While the Singleton pattern can be useful for managing global state, it is important to be cautious when using it. Global state can make it difficult to understand the behavior of a system and can lead to unpredictable results.

- Consider using dependency injection: Instead of using the Singleton pattern to manage global state, consider using dependency injection to manage the lifetime of objects. This can make it easier to test the system and can help to reduce the coupling between classes.

- Avoid violating the Single Responsibility Principle: It is important to ensure that the Singleton class has only one responsibility and is not overloaded with multiple responsibilities. This can make the class difficult to maintain and can lead to bugs and inconsistencies.

### FAQ

- [Are Singletons really that bad?](https://stackoverflow.com/questions/1020312/are-singletons-really-that-bad?noredirect=1&lq=1)
