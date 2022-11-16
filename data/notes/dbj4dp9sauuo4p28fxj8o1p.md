
Application context is responsible for creating and managing all the beans.

```java
@SpringBootApplication
public class SpringIn10StepsApplication {

 public static void main(String[] args) {
  // Returns an application context
  ApplicationContext applicationContext = SpringApplication.run(SpringIn10StepsApplication.class, args);
  // Getting the bean from the application context
  BinarySearchImpl binarySearch = applicationContext.getBean(BinarySearchImpl.class);
  int result = binarySearch.binarySearch(new int[] {12,4,6}, 3);
 }

}
```
