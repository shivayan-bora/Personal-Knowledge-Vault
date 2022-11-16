
```java
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SpringIn10StepsApplication {

    public static void main(String[] args) {
    BinarySearchImpl binarySearch = new BinarySearchImpl(new BubbleSortAlgorithm());
    int result = binarySearch.binarySearch(new int[] {12,4,6}, 3);
    System.out.println(result);

    SpringApplication.run(SpringIn10StepsApplication.class, args);
    }
}
```

Spring boot would automatically scan the package and it's subpackages where the main application class is present for managing beans and dependencies. This is called component scan.

`@SpringBootApplication` denotes the main application class.
