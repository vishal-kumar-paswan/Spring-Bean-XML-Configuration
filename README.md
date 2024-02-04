## Spring Bean XML Configuration

As we know how SpringBoot handles the containers, we can achieve the same thing in Spring using the XML configurations.
<br/>
For that we first need to add the [Spring Context](https://mvnrepository.com/artifact/org.springframework/spring-context) into the `pom.xml`. Next we have to configure the Configuration file where we will store all the beans we want.
For that we will be creating a `resourses` directory where we will create the XML configuration file, say `spring.xml`,

Then we will add the `bean` in it. For that, we will use `id` which we will use to refer the class and `class` which is the package name we are referring to.

```
<bean id="student" class="org.vishal.Student">
</bean>
```

Now to access the bean from the container, we have to create the `ApplicationContext` context. Since we are not using SpringBoot, we to load the configuration by ourselves and we do that using the `ClassPathXmlApplicationContext`.
In the `ClassPathXmlApplicationContext`,  we simply pass the XML config file in double quotes.
```
ApplicationContext context = new ClassPathXmlApplicationContext("spring.xml"); // File name here
```

Now to get the bean from the container, we use the `getBean()` method and pass the id we used for creating the bean in the XML config file.
```
Student student =(Student) context.getBean("student"); // Passing bean id we used in XML config
```
