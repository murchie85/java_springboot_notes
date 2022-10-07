# JAVA AND SPRINGBOOT COMPENDIUM  


- [jump to javaSetup](#JAVA-SETUP)
- [jump to JAVA NOTES](#JAVA-NOTES)  

  
# SPRINGBOOT NOTES 

|  **SPRING**  |  **SPRINGBOOT**  |
|----|----|
| It aims to simplify Java EE development that makes developers more productive.| It aims to shorten the code length and provide the easiest way to develop Web Applications.|
| The primary feature of the Spring Framework is dependency injection.| The primary feature of Spring Boot is Autoconfiguration. It automatically configures the classes based on the requirement.|
| To test the Spring project, we need to set up the sever explicitly.|Spring Boot offers embedded server such as Jetty and Tomcat, etc. |
  


|  **SPRING Boot**  |  **Spring MVC**  |
|----|----|
| Spring Boot is a module of Spring for packaging the Spring-based application with sensible defaults.| Spring MVC is a model view controller-based web framework under the Spring framework.|
| There is no requirement for a deployment descriptor. |	A Deployment descriptor is required.|  
    
## Spring Boot Architecture  

![](https://static.javatpoint.com/springboot/images/spring-boot-architecture.png)
  
  
![](https://static.javatpoint.com/springboot/images/spring-boot-architecture2.png)    

- Ensure validator classes, view classes, and utility classes.
- Creates a data access layer and performs CRUD operation.
- The client makes the HTTP requests (PUT or GET).
- The request goes to the controller, and the controller maps that request and handles it. After that, it calls the service logic if required.
- In the service layer, all the business logic performs. It performs the logic on the data that is mapped to JPA with model classes.
- A JSP page is returned to the user if no error occurred.

# JAVA NOTES 


# INTERFACES & ABSTRACTIONS WITH EXAMPLE

Lets assume we have set up an bird class, animal class and now define the zoo class which instantiates the objects. 

**ZOO CLASS**
```java

public class zoo(){
	Animal animal1 = new Animal(12,'M',23);
	animal1.eat()


	Bird.bird1 = new Bird(3,'F',10);
	bird1.eat()
	bird1.sleep()
}

```

The bird class extends the animal class ...

**BIRD CLASS**
```java

public class Bird extends Animal(){

	public Bird(int age, String gender, int weightInLbs){
		super(age,gender weightInLbs)// super means to use parms from parent class i.e. animal
	}

	// adding fly

	publi void fly(){
		System.out.println("Flying.....")
	}


}
```


**METHOD OVERRIDE**  

But not all birds can fly 


**CHICKEN CLASS**
```java

public class Bird extends Animal(){

	public Bird(int age, String gender, int weightInLbs){
		super(age,gender weightInLbs)// super means to use parms from parent class i.e. animal
	}

	// METHOD OVERRIDING

	publi void fly(){
		System.out.println("I can't fly.....")
	}


}
```  
  
SO if we create a chicken and make it fly, it will use the new deifned method, which overrides the old one . 


```java

public class zoo(){
	Chicken.chick = new Chicken(3,'F',10);
	bird1.fly()
}

```
   
Output....  

```shell
"I can't fly....."
```
  
## CREATING THE INTERFACE AND ABSTRACT CLASS   
  
A better way to do this is to :   
  
- remove the `fly()` method
- create an interface called flyable
- make it abstract
	- which forces users to populate it when inheriting

```java
public interface Flyable{
	// thats it - now the user must define
	public void fly();
}

```





# JAVA SETUP

## Setting up Java on Mac
     
1. Go to Maven site, download .tgz binary (top) and extract to `/Application`  
2. **Install Java JDK** via oracle - requires a lot of digging through the sight, as standard is only to include JRE.
3. Set the following environment variables:  
```shell
export JAVA_HOME=$(/usr/libexec/java_home)
export M2_HOME=/Applications/apache-maven-3.8.6
export PATH=$PATH:$M2_HOME/bin
```

  
- Avoid `brew install java` and `brew install maven`  
  - This is because home isn't properly set, java doesn't include JDK etc.  



# USEFUL LINKS

https://spring.io/guides/gs/maven/#scratch  
https://spring.io/guides/gs/maven/  
