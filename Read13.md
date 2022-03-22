# One-to-Many Relationship
A one-to-many relationship is defined using the @OneToMany and @ManyToOne annotations and can have the optional @RestResource annotation to customize the association resource.
# I will to show example to explain this relationship
## 1. The Data Model   
, let's add a new Book entity that will represent the “many” end of a relationship with the Library entity:  
* Book entity
    @Entity  
    public class Book {  

        @Id  
        @GeneratedValue  
        private long id;  
        
        @Column(nullable=false)  
        private String title;  
        
        @ManyToOne  
        @JoinColumn(name="library_id")  
        private Library library;  
        
        // standard constructor, getter, setter    
    }  
* Library entity 
public class Library {  

    @OneToMany(mappedBy = "library")  
    private List<Book> books;  

}  

## 2. The Repository   
we need to create a Repository such as Repository for Book class:  
public interface BookRepository extends CrudRepository<Book, Long> { }
## 3. The Association Resources   
In order to add a book to a library, we need to create a Book instance first by using the /books collection resource:  
curl -i -X POST -d "{\"title\":\"Book1\"}"  
  -H "Content-Type:application/json" <http://localhost:8080/books>

# Integration Testing in Spring
## 1. Introduction 
integration testiong plays an important role in the application development cycle by verifying the end-to-end behavior of a system. 
## 2. Prepration
We'll nedd several maven or gradle dependencies for running the integration tests we'll use in this articals, First and foremost we'll need the latest 
1. junit-jupiter-engine
2. junit-jupiter-api
3. Spring test 
For effective asserting of results, we'll also use : 
1. Hamcrest .  
2. JSON path.  
## 3. Spring MVC Test configuration 
Now let's see how to configure and run the Spring enabled tests.

### 1. Enable Spring in Tests With JUnit 5
JUnit 5 defines an extension interface through which classes can integrate with the JUnit test.

We can enable this extension by adding the @ExtendWith annotation to our test classes and specifying the extension class to load. To run the Spring test, we use SpringExtension.class.

We'll also need the @ContextConfiguration annotation to load the context configuration and bootstrap the context that our test will use.  
* Example :   
@ExtendWith(SpringExtension.class)  
@ContextConfiguration(classes = { ApplicationConfig.class })   
@WebAppConfiguration  
public class GreetControllerIntegrationTest {  
    ....
}    
Notice that in @ContextConfiguration, we provided the ApplicationConfig.class config class, which loads the configuration we need for this particular test.  
* Example :   
@ContextConfiguration(locations={""})  
Finally, we'll also annotate the test with @WebAppConfiguration, which will load the web application context.  
* Example :  
@WebAppConfiguration(value = "")

### 2. The WebApplicationContext Object
WebApplicationContext provides a web application configuration. It loads all the application beans and controllers into the context.  

Now we'll be able to wire the web application context right into the test:  

* @Autowired  
private WebApplicationContext webApplicationContext;  
### 3. Mocking Web Context Beans 
MockMvc provides support for Spring MVC testing. It encapsulates all web application beans and makes them available for testing.  
### 4. Verify Test Configuration   
Notice that we're also checking that a GreetController.java bean exists in the web context. This ensures that Spring beans are loaded properly. At this point, the setup of the integration test is done. Now, we'll see how we can test resource methods using the MockMvc object.  
## 4. Writiong Integration Tests
### 1. Verify View Name with this endpoint 
http://localhost:8080/spring-mvc-test/
### * we have method inside it  

1. perform() :we can have assertion expectations about the response, like its content, HTTP status, or header.
2. andDo(pring()) : will print the request and response. This is helpful to get a detailed view in case of an error.
3. andExpect() : will expect hte provided argument.
### 2. Verify Response Body
http://localhost:8080/spring-mvc-test/greet

### * we have method inside it  

1. andExpect(MockMvcResultMatchers.status().isOk()) will verify that response HTTP status is Ok (200). This ensures that the request was successfully executed.
2. andExpect(MockMvcResultMatchers.jsonPath(“$.message”).value(“Hello World!!!”)) will verify that the response content matches with the argument “Hello World!!!” Here, we used jsonPath, which extracts the response content and provides the requested value.
3. andReturn() will return the MvcResult object,

### 3. Send GET Request with path Variable
<http://localhost:8080/spring-mvc-test/greetWithPathVariable/John>

### 4. Send GET Request With Query Parameters
<http://localhost:8080/spring-mvc-test/greetWithQueryVariable?name=John%20Doe>
### 5. Send POST Request
<http://localhost:8080/spring-mvc-test/greetWithPost>
MockMvcRequestBuilders.post(“/greetWithPost”) will send the POST request. We can set path variables and query parameters in a similar way as before, whereas form data can be set only via the param() method, similar to query parameters as:
## 5. MockMvc LImitations
MockMvc provides an elegant and easy-to-use API to call web endpoints and to inspect and assert their response at the same time. Despite all its benefits, it has a few limitations.
