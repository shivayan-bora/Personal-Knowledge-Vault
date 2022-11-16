
To do this in Spring:

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

@Component: Tells the spring framework that you need to manage instances of the annotated class.

@Autowired: Tells the spring to start looking for the annotated dependency among the component it manages.
