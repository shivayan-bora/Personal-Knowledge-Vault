---
id: 1ix8yz4lp54qkh6w5xj5tzi
title: Inversion of Control
desc: ''
updated: 1659282036863
created: 1659281745176
---

Consider this example.

```java
public class ComplexBusinessService {
    // Creates a new instance of a BubbleSortAlgorithm class
    SortAlgorithm sortAlgorithm = new BubbleSortAlgorithm();
    ...
}

public class BubbleSortAlgorithm implements SortAlgorithm {...}
```

Here the Class which needs the dependency is creating the instance of the dependency.

However in the below example, Spring is the one that's creating the instance of the dependency:

```java
@Component
public class ComplexBusinessService {
    @Autowired
    SortAlgorithm sortAlgorithm;
    ...
}

@Component
public class BubbleSortAlgorithm implements SortAlgorithm {...}
```

Spring takes the control from the class that needs the dependency to create an instance of the dependency. This is called Inversion of Control.
