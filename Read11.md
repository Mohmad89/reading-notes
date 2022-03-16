# Spring MVC and Thymeleaf : how to access data from templates .
In a typical Spring MVC application, @Controller classes are responsible for preparing a model map with data and selecting a view to be rendered. This model map allows for the complete abstraction of the view technology and, in the case of Thymeleaf, it is transformed into a Thymeleaf context object (part of the Thymeleaf template execution context) that makes all the defined variables available to expressions executed in templates.

* ## Spring model attributes

    * Spring MVC calls the pieces of data that can be accessed during the execution of views model attributes. The equivalent term in Thymeleaf language is context variables.  

    * There are several ways of adding model attributes to a view in Spring MVC. Below you will find some common cases:  
1. Add attrubute to Model via its addAttribute :   
EX : 
@RequestMapping(value = "message", method = RequestMethod.GET)  
        public String messages(Model model) {  
            model.addAttribute("messages",   messageRepository.findAll());  
            return "message/list";    
        }  
2. Return modelAndView with model attributes included :   
 @RequestMapping(value = "message", method = RequestMethod.GET)    
        public ModelAndView messages() {    
            ModelAndView mav = new ModelAndView("message/list");  
            mav.addObject("messages", messageRepository.findAll());  
            return mav;  
        }
3. Expose common attributes via methods annotated with @ModelAttribute :  
  @ModelAttribute("messages")  
        public List<Message> messages() {  
            return messageRepository.findAll();  
        }  
* ## Request parameters
    Request parameters can be easily accessed in Thymeleaf views. Request parameters are passed from the client to server like:  
    <https://example.com/query?q=Thymeleaf+Is+Great>!  
In order to access the q parameter you can use the param. prefix:    
Another way to access request parameters is by using the special #request object that gives you direct access to the javax.servlet.http.HttpServletRequest object:  
Ex:   
    <p th:text="${#request.getParameter('q')}" th:unless="${#request.getParameter('q') == null}">Test</p>

* ## Session attributes   
    Example to add mySessionAttribute to session :  

    @RequestMapping({"/"})  
        String index(HttpSession session) {  
            session.setAttribute("mySessionAttribute",  "someValue");  
            return "index";  
        }  
* ## ServletContext attributes 
    The ServletContext attributes are shared between requests and sessions. In order to access ServletContext attributes in Thymeleaf you can use the #servletContext. prefix:
* ## Spring beans 
    Thymeleaf allows accessing beans registered at the Spring Application Context with the @beanName syntax.
___

# Serving Web Content with Spring MVC

1. Spring initializr 
    1. Navigate to <https://start.spring.io>. This service pulls in all the dependencies you need for an application and does most of the setup for you.

    2. Choose either Gradle or Maven and the language you want to use. This guide assumes that you chose Java.

    3. Click Dependencies and select Spring Web, Thymeleaf, and Spring Boot DevTools.

    4. Click Generate.
2. Create a Web Controller  
    In Spring’s approach to building web sites, HTTP requests are handled by a controller. You can easily identify the controller by the @Controller annotation. In the following example, GreetingController handles GET requests for /greeting by returning the name of a View (in this case, greeting). A View is responsible for rendering the HTML content.  
The @GetMapping annotation ensures that HTTP GET requests to /greeting are mapped to the method.
* ## Spring Boot DevTools
         A common feature of developing web applications is coding a change, restarting your application, and refreshing the browser to view the change. This entire process can eat up a lot of time. To speed up this refresh cycle, Spring Boot offers with a handy module known as spring-boot-devtools.
* Spring Boot DevTools is :  
    1. Enables hot swapping.
    2. Switches template engines to disable caching.
        * you can modify the source code and see the changes immediately, simply by reloading the page in the web browser, without rebuilding your project and have to restart the web server
    3. Enables LiveReload to automatically refresh the browser.
    4. Other reasonable defaults based on develpment instead of production.
* ## Run the Application 
        The Spring Initializr creates an application class for you. In this case, you need not further modify the class provided by the Spring Initializ    
     @SpringBootApplication is a convenience annotation that adds all of the following:  
1. @Configuration: Tags the class as a source of bean definitions for the application context.

2. @EnableAutoConfiguration: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings. For example, if spring-webmvc is on the classpath, this annotation flags the application as a web application and activates key behaviors, such as setting up a DispatcherServlet.

3. @ComponentScan: Tells Spring to look for other components, configurations, and services in the com/example package, letting it find the controllers.
* ## Bulid an executable JAR 
        You can run the application from the command line with Gradle or Maven. You can also build a single executable JAR file that contains all the necessary dependencies, classes, and resources and run that. Building an executable jar makes it easy to ship, version, and deploy the service as an application throughout the development lifecycle, across different environments, and so forth.
___