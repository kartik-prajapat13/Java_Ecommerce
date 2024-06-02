
## New Upgrade ( what's new)
- Hibernate configuration added( database and tables automatically create when run the project)
- Service classes provide reusable services throughout project
- dao classes interact with database 
- bug fixed ( product image, security , etc..)
- support in both eclipse & intellij ide
- overall redesign entire code that help reusability. 
- disclaimer: currently working on this branch so there may be some bug related to endpoint, and working on cart logic.
  

### Database

MySQL or MariaDB can be used as the database for this project. The database connection can be configured in the `application.properties` file, with the appropriate values for the following properties:
(you'd better use another username not root)
```properties
    db.url=jdbc:mysql://[ip address of db]:[port of db]/ecommjava?createDatabaseIfNotExist=true
    db.username=[username]
    db.password=[password, if any]
```

### Web Directories

The views are located in `src/main/webapp/views`, but for some reason, Spring Boot doesn't recognize that directory. To remedy this, you must change the working directory of the project in your IDE. If you're using IntelliJ IDEA, follow these steps:

1. Click on the "Edit Configurations..." button in the top right corner of the IDE
2. Click on the `JtSpringProjectApplication` configuration
3. Change the "Working directory" option (if not present, click on "Modify Options" and select from the list) to the `$MODULE_WORKING_DIR$` macro
4. Click "Apply" and "OK"


When you run the project, the views should be found by Spring Boot and you should see a login page in http://localhost:8080/ (if not logged in previously)!
![configurations](image.png)


### Controller
- control the endpoint and also send data to view( we use ModelAndView method)
- ``` @GetMapping("login")
	public String adminlogin() {
		
		return "adminlogin";
	}```
- whenever /login url is hit , src->main->webapp-> adminlogin.jsp file execute
### Models
- represent data as entity and relationship among them.

### View
- receive data from controller and show with frontend.

## Endpoints
- http://localhost:8080/
- http://localhost:8080/register
- http://localhost:8080/admin/products
- http://localhost:8080/admin/customers
- http://localhost:8080/admin/categories
- http://localhost:8080/admin/Dashboard


### Reference Documentation
For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/2.6.4/maven-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/2.6.4/maven-plugin/reference/html/#build-image)
* [Spring Web](https://docs.spring.io/spring-boot/docs/2.6.4/reference/htmlsingle/#boot-features-developing-web-applications)



