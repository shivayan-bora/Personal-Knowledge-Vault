
The process where Spring framework identifies the dependencies, and populates them. e.g.

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

@Autowired tells Spring that `SortAlgorithm` is a dependency for the `ComplexBusinessService`.
