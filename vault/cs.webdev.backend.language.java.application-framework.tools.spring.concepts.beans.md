---
id: rqnt9wfj3z06brctntvc288
title: Beans
desc: ''
updated: 1659281539140
created: 1659275656747
---

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
