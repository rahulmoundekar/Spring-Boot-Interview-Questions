# Spring-Boot-Interview-Questions

### 1. What is Spring Boot?
First of all Spring Boot is not a framework, it is a way to ease to create stand-alone application with minimal or zero configurations. It is approach to develop spring based application with very less configuration. It provides defaults for code and annotation configuration to quick start new spring projects within no time. It leverages existing spring projects as well as Third party projects to develop production ready applications. It provides a set of Starter Pom’s or gradle build files which one can use to add required dependencies and also facilitate auto configuration.
Spring Boot automatically configures required classes depending on the libraries on its classpath. Suppose your application want to interact with DB, if there are Spring Data libraries on class path then it automatically sets up connection to DB along with the Data Source class.

### 2. What are the advantages of using Spring Boot?
- It is very easy to develop Spring Based applications with Java or Groovy.
- It reduces lots of development time and increases productivity.
- It avoids writing lots of boilerplate Code, Annotations and XML Configuration.
- It is very easy to integrate Spring Boot Application with its Spring Ecosystem like Spring JDBC, Spring ORM, Spring Data, Spring Security etc.
- It follows “Opinionated Defaults Configuration” Approach to reduce Developer effort
- It provides Embedded HTTP servers like Tomcat, Jetty etc. to develop and test our web applications very easily.
- It provides CLI (Command Line Interface) tool to develop and test Spring Boot (Java or Groovy) Applications from command prompt very easily and quickly.
- It provides lots of plugins to develop and test Spring Boot Applications very easily using Build Tools like Maven and Gradle
- It provides lots of plugins to work with embedded and in-memory Databases very easily.

### 3. What are the disadvantages of using Spring Boot?
It is very tough and time consuming process to convert existing or legacy Spring Framework projects into Spring Boot Applications. It is applicable only for brand new/Greenfield Spring Projects.

### 4. Why is it “opinionated”?
It follows “Opinionated Defaults Configuration” Approach to reduce Developer effort. Due to opinionated view of spring boot, what is required to get started but also we can get out if not suitable for application.
-   Spring Boot uses sensible defaults, “opinions”, mostly based on the classpath contents.
-   For example
-  Sets up a JPA Entity Manager Factory if a JPA implementation is on the classpath.
- Creates a default Spring MVC setup, if Spring MVC is on the classpath.
-  Everything can be overridden easily
-  But most of the time not needed

### 5. How does it work? How does it know what to configure?
-  Auto-configuration works by analyzing the classpath
-  If you forget a dependency, Spring Boot can’t configure it
-  A dependency management tool is recommended
-  Spring Boot parent and starters make it much easier
-  Spring Boot works with Maven, Gradle, Ant/Ivy
-  Our content here will show Maven

### 6. How are properties defined? Where?
In spring boot, we have to define properties in the application.properties file exists in classpath of application as follow.

Example: configure default DataSource bean
database.host=localhost
database.user=admin

### 7. What is the difference between an embedded container and a WAR?
There is no force to go container less
-  Embedded container is just one feature of Spring Boot
-  Traditional WAR also benefits a lot from Spring Boot
-  Automatic Spring MVC setup, including DispatcherServlet
-  Sensible defaults based on the classpath content
-  Embedded container can be used during development

### 8. What embedded containers does Spring Boot support?
Spring Boot includes support for embedded Tomcat, Jetty, and Undertow servers.
By default the embedded server will listen for HTTP requests on port 8080.

### 9. What does @EnableAutoConfiguration do? What about @SpringBootApplication?
@EnableAutoConfiguration annotation on a Spring Java configuration class
– Causes Spring Boot to automatically create beans it thinks you need
– Usually based on classpath contents, can easily override
                    
                    @Configuration
                    @EnableAutoConfiguration
                    public class MyAppConfig {
                          public static void main(String[] args) {
                          SpringApplication.run(MyAppConfig.class, args);
                       }
                    }
                    
@SpringBootApplication was available from Spring Boot 1.2
It is very common to use @EnableAutoConfiguration, @Configuration, and @ComponentScan together.
      
      @Configuration
      @ComponentScan
      @EnableAutoConfiguration
      public class MyAppConfig {
              ...
      }
      
      With @SpringBootApplication annotation
      @SpringBootApplication
      public class MyAppConfig {
              ...
      }

