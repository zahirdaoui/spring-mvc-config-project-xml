# Spring MVC XML-based Example Project

## Description

This is a simple **Spring MVC project** configured using **XML**, demonstrating the core concepts of the Spring Web MVC framework. The project showcases how HTTP requests are handled using **DispatcherServlet**, mapped to **Controllers**, and rendered through **Views** using a **View Resolver**.

---

## Features

### 1. DispatcherServlet
- The **DispatcherServlet** acts as the **front controller** in Spring MVC.
- It intercepts all incoming HTTP requests and dispatches them to the appropriate **Controllers** based on URL mappings.
- Configured in `web.xml` for XML-based setup.

### 2. Controllers
- Controllers handle the business logic and define endpoints for incoming HTTP requests.
- Annotated with `@Controller` and use `@GetMapping` or `@PostMapping` to map URLs.
- Example:
```java
@GetMapping("/")
public String home(Model model) {
    model.addAttribute("message", "Welcome to Spring MVC!");
    return "home";
}
3. View Resolver

The View Resolver maps logical view names returned by controllers to actual view files.

In this project, an InternalResourceViewResolver is used for JSP views.

Example configuration:

<bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
    <property name="prefix" value="/WEB-INF/views/"/>
    <property name="suffix" value=".jsp"/>
</bean>

4. Views

Views are the front-end components (JSP files) rendered by the controller.

This project uses JSPs located in WEB-INF/views/.

Example:

<h1>${message}</h1>


Data from the controller is passed via the Model object.
