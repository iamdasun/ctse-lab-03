# Product Service

A simple Spring Boot microservice for managing products, developed for SLIIT SE4010 DevOps Lab 3.

## Project Overview

- **Project Name**: product-service
- **Group ID**: com.sliit
- **Artifact ID**: product-service
- **Java Version**: 17
- **Spring Boot Version**: 3.5.10

## Technology Stack

- Spring Boot 3.5.10
- Spring Web
- Spring Data JPA
- H2 Database (In-Memory)
- Springdoc OpenAPI (Swagger UI)
- Lombok

## Folder Structure

```
product-service/
├── pom.xml
├── src/
│   ├── main/
│   │   ├── java/com/sliit/productservice/
│   │   │   ├── ProductServiceApplication.java
│   │   │   ├── entity/
│   │   │   │   └── Product.java
│   │   │   ├── repository/
│   │   │   │   └── ProductRepository.java
│   │   │   └── controller/
│   │   │       └── ProductController.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/
└── README.md
```

## Build and Run

### Prerequisites

- Java 17 or higher
- Maven

### Build the Project

```bash
./mvnw clean package
```

### Run the Application

```bash
./mvnw spring-boot:run
```

The application will start on `http://localhost:8081`

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/products | Create a new product |
| GET | /api/products | Get all products |
| GET | /api/products/{id} | Get product by ID |
| DELETE | /api/products/{id} | Delete product by ID |

### Example Request

**Create Product**
```bash
curl -X POST http://localhost:8081/api/products \
  -H "Content-Type: application/json" \
  -d '{"name": "Laptop", "price": 999.99}'
```

**Get All Products**
```bash
curl http://localhost:8081/api/products
```

**Get Product by ID**
```bash
curl http://localhost:8081/api/products/1
```

**Delete Product**
```bash
curl -X DELETE http://localhost:8081/api/products/1
```

## Access H2 Console

The H2 database console is enabled for development purposes.

**URL**: http://localhost:8081/h2-console

**JDBC URL**: jdbc:h2:mem:productdb

**Username**: sa

**Password**: (empty)

## Access Swagger UI

Swagger UI provides interactive API documentation.

**URL**: http://localhost:8081/swagger-ui.html

## Access OpenAPI Documentation

OpenAPI 3.0 JSON documentation is available at:

**URL**: http://localhost:8081/v3/api-docs

## Configuration

The application uses the following configuration in `application.properties`:

```properties
# H2 Database Configuration
spring.datasource.url=jdbc:h2:mem:productdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=

# JPA Configuration
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# H2 Console
spring.h2.console.enabled=true
```

## License

This project is for educational purposes as part of SLIIT SE4010 DevOps Lab 3.
