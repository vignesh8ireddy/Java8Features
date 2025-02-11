## Java 5 features (Tiger)
1. static import
2. @Override annotation
3. covariant returns
4. Autoboxing & Auto unboxing
5. Var-arg parameter method
6. for-each (i.e enhanced for loop)
7. Generics
8. Enumerations
9. Annotations (meta-data)
10. java.lang.concurrent package (collection api with thread safety)
11. C style formatting input and output
12. Scanner class

Java 5 is a failed version, because of all the above features, its execution has become slow
and to solve this Java 6 has came.

## Java 6 features (Mustang)
1. Console
2. NavigableSet & NavigableMap

## Java 7 features (Dolphin)
1. Execution flow change with respect to main method
2. Binary Literal is also introduced to decimal, octal and hexadecimal integer literals
3. Underscore in number literal
4. Switch with String argument
5. try with resource
6. Catch with multiple exception classes
7. Generic type inference (<>)
8. var-arg bug fix in overloading and overriding methods 

In 2010, Oracle corporation acquired Sun Microsystems including java

## Java 8 features

1. Default Methods in interface
2. Static Methods in interface
3. Functional Interface, @FunctionalInterface annotation, Lambda Expression
    * Functional Interface is SAM i.e Single Abstract Method Interface
    * Comparable, Comparator, Runnable, Callable,... are few functional interfaces
    * Functional interface is used for enabling Functional Programming to java.
    * Functional interface is also used for defining lambda expressions to pass a function
      directly as an argument to method.
    * Because we define lambda expression from functional interface, we can also say a functional
      interface is a Base type/ Super type of the Lambda Expression
    * Two ways of creating functional interface:
      1. effectively creating a functional interface
         ```java
         //you are commited to not add any other method signature to below interface
         //that's why is effective
         interface Addition {
              void add(int a, int b);
         }
         ```
      2. using @FunctionalInterface:
         ```java
         // if you try to add any other method signature, compiler throws error
         // i.e you are forcing the below interface to be a functional interface
         @FunctionalInterface
         interface Addition {
             void add(int a, int b);
         }
         ```
    * The following are the programming elements that are allowed to place in the
      functional interface:
      1. public static final fields
      2. public static inner classes
      3. public default implemented methods
      4. public static implemented methods
      5. private static and non-static methods (java 9+)
      6. 11 methods of java.lang.Object as abstract methods
      7. only one public abstract method
    * Inheritance among functional interfaces
      ```java
      @FunctionalInterface
      interface F1 {
         void m1();
      }
      
      @FunctionalInterface
      interface F2 extends F1 {//throws error, because 2 public abstract methods
         void m2();
      }
      
      @FunctionalInterface
      interface F3 extends F1 {//allowed because only one public abstract method
      }
      
      @FunctionalInterface
      interface F4 extends F1 {//allowed
         public default void m4();
      }
      ```
    * Generic Functional Interface
      ```java
      @FuntionalInterface
      interface F1<T> {
        T m1(T a, T b);
      }
      
      @FunctionalInterface
      interface Addition<T extends Number> {
        T add(T a, T b);
      }
      ```
    * Lambda Expression
   
4. Functional API (java.util.function)
   * Consumer<T>
   * Supplier<T>
   * Function<T,R>
   * Predicate<T>
5. Method and Constructor reference (::)
6. forEach() method and specialIterator method in Iterable interface
7. Stream API (java.util.stream)
8. New Date & Time API
9. Optional API