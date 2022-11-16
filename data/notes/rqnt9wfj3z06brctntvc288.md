
The instances that Spring manages are called beans. e.g.

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

`ComplexBusinessService` and `BubbleSortAlgorithm` are two beans.
