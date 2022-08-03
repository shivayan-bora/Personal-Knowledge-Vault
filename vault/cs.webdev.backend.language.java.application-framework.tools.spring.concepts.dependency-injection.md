---
id: 8zi6m0lp6lz6wsx9w89wqlr
title: Dependency Injection
desc: ''
updated: 1659281697594
created: 1659248758307
---

Let's consider a simple example:

```java
public class ComplexBusinessService {
    SortAlgorithm sortAlgorithm;
    ...
}

public class BubbleSortAlgorithm implements SortAlgorithm {...}
```

Here we have a `ComplexBusinessService` class which needs another class `SortingAlgorithm` to perform some sort of sorting which aids in the business logic. We can say, the `ComplexBusinessService` is dependent on `SortingAlgorithm`.

Likewise, in a bigger web application, we have thousands of classes and each class needs some other class to perform it's function, i.e. those classes need other classes as a dependency. So, in a typical application, you will have a lot of classes with a lot of dependency.

Before Spring came into picture, this is how we used to manage dependencies:

```java
public class ComplexBusinessService {
    // Creates a new instance of a BubbleSortAlgorithm class
    SortAlgorithm sortAlgorithm = new BubbleSortAlgorithm();
    ...
}

public class BubbleSortAlgorithm implements SortAlgorithm {...}

```

`ComplexBusinessService` directly instantiates an object of `BubbleSortAlgorithm` class. If we would need our service to use a quick sort algorithm, we need to modify the code. This is called tight coupling i.e., `ComplexBusinessService` is tightly couple with `BubbleSortAlgorithm`, which is not considered a good practice.

To fix this, we would need to do the following:

```java
public class ComplexBusinessService {
    SortAlgorithm sortAlgorithm; // = new BubbleSortAlgorithm();
    // Creates a constructor to accept a SortAlgorithm type object and instantiate our sorting algorithm
    public ComplexBusinessService(SortAlgorithm sortAlgorithm) {
        this.sortAlgorithm = sortAlgorithm;
    }
    ...
}
```

Now whoever is using the `ComplexBusinessService`, can pass the type of`SortAlgorithm` to the constructor of `ComplexBusinessService`.

```java
SortAlgorithm sortAlgorithm = new BubbleSortAlgorithm();
ComplexBusinessService businessService = new ComplexBusinessService(sortAlgorithm);
```

All the code is doing is creating object and populating the dependencies. This is Dependency Injection.
