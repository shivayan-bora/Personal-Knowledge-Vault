---
id: lnbhdefgg0kjjwe19qan3nr
title: Auto Wiring
desc: ''
updated: 1659281655318
created: 1659281571961
---

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
