Spring Boot CRUD Application
Overview
This project is a Spring Boot-based CRUD application that demonstrates the following functionalities:
•	Category and Product management with CRUD operations.
•	One-to-Many relationship between Category and Product.
•	RESTful APIs for managing Categories and Products.
•	Pagination support for fetching records.
•	Database integration using MySQL with JPA and Hibernate.
Features
1.	Category CRUD Operations:
o	Create, Read, Update, and Delete categories.
o	Pagination support for fetching categories.
2.	Product CRUD Operations:
o	Create, Read, Update, and Delete products.
o	Pagination support for fetching products.
o	Fetch a product with its associated category details.
3.	Database Configuration:
o	MySQL database integration.
o	Annotation-based configuration (no XML).
Prerequisites
•	Java 17 or higher
•	Maven
•	MySQL Server
•	Postman or any API testing tool (optional)
Getting Started
1. Clone the Repository
git clone <repository-url>
cd <repository-directory>
2. Database Setup
1.	Start your MySQL server.
2.	Create a database: 
3.	CREATE DATABASE testdb;
4.	(Optional) Create a new user and grant permissions: 
5.	CREATE USER 'springuser'@'localhost' IDENTIFIED BY 'password';
6.	GRANT ALL PRIVILEGES ON testdb.* TO 'springuser'@'localhost';
7.	FLUSH PRIVILEGES;
3. Configure the Application
Update the src/main/resources/application.properties file with your database details:
spring.datasource.url=jdbc:mysql://localhost:3306/testdb
spring.datasource.username=springuser
spring.datasource.password=password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
4. Build and Run the Application
1.	Build the project using Maven: 
2.	mvn clean install
3.	Run the application: 
4.	mvn spring-boot:run
5. Test the APIs
Use Postman or any other API testing tool to test the endpoints.
Category Endpoints
1.	Get all categories (paginated):
2.	GET http://localhost:8080/api/categories?page=0
3.	Create a new category:
4.	POST http://localhost:8080/api/categories
5.	Content-Type: application/json
6.	{
7.	    "name": "Electronics"
8.	}
9.	Get category by ID:
10.	GET http://localhost:8080/api/categories/{id}
11.	Update category by ID:
12.	PUT http://localhost:8080/api/categories/{id}
13.	Content-Type: application/json
14.	{
15.	    "name": "Updated Category Name"
16.	}
17.	Delete category by ID:
18.	DELETE http://localhost:8080/api/categories/{id}
Product Endpoints
1.	Get all products (paginated):
2.	GET http://localhost:8080/api/products?page=0
3.	Create a new product:
4.	POST http://localhost:8080/api/products
5.	Content-Type: application/json
6.	{
7.	    "name": "Smartphone",
8.	    "price": 699.99,
9.	    "category": {
10.	        "id": 1
11.	    }
12.	}
13.	Get product by ID:
14.	GET http://localhost:8080/api/products/{id}
15.	Update product by ID:
16.	PUT http://localhost:8080/api/products/{id}
17.	Content-Type: application/json
18.	{
19.	    "name": "Updated Product Name",
20.	    "price": 799.99,
21.	    "category": {
22.	        "id": 1
23.	    }
24.	}
25.	Delete product by ID:
26.	DELETE http://localhost:8080/api/products/{id}
Project Structure
src/main/java/com/example/demo
    ├── Controller
    │   ├── CategoryController.java
    │   └── ProductController.java
    ├── Entity
    │   ├── Category.java
    │   └── Product.java
    ├── Repository
    │   ├── CategoryRepository.java
    │   └── ProductRepository.java
    ├── Service
    │   ├── CategoryService.java
    │   └── ProductService.java
    └── DemoApplication.java
src/main/resources
    ├── application.properties
Technologies Used
•	Spring Boot: Framework for building Java applications.
•	Spring Data JPA: ORM for database interaction.
•	Hibernate: ORM implementation.
•	MySQL: Relational database.
•	Maven: Build and dependency management tool.
•	Postman: API testing tool.


