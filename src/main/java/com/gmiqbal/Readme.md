# Annotation Explanation
## @SpringBootApplication
This is the main class for a Spring Boot application, and it enables auto-configuration of various components, including Spring MVC for handling HTTP requests and responses.
`@SpringBootApplication` is shortcut for these below lines:
```
@ComponentScan( basePackages = "com.gmiqbal" )
@EnableAutoConfiguration
@Configuration
```
## @RestController
This class is a Spring MVC controller, and all the methods in the class will handle HTTP requests.
`@RestController` is shortcut for below lines:
```
@Controller
@ResponseBody
```

## record GreetResponse(String greet){}
`record GreetResponse(String greet){}` is shortcut for all the below lines:
```
class GreetResponse{
        private final String greet;
        
        //constructor
            public GreetResponse(String greet) {
                this.greet = greet;
            }
            
        //getter - important!
            public String getGreet() {
                return greet;
            }
            
        //toString
            @Override
            public String toString() {
                return "GreetResponse{" +
                        "greet='" + greet + '\'' +
                        '}';
            }

        //equals
            @Override
            public boolean equals(Object o) {
                if (this == o) return true;
                if (o == null || getClass() != o.getClass()) return false;
                GreetResponse that = (GreetResponse) o;
                return Objects.equals(greet, that.greet);
            }
            
        //hashcode
            @Override
            public int hashCode() {
                return Objects.hash(greet);
            }
    }
```