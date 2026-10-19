# Student Manager

A Spring Boot web application for managing student records. The app allows users to add, view, update, and delete student information, with validation rules for each field and persistence in an H2 database.

## Features

- Add new students with validation
- View all registered students in a table
- Edit existing student records
- Delete student records
- Prevent duplicate email addresses
- Store data in an embedded H2 database
- Built with Spring MVC + Thymeleaf templates

## Tech Stack

- Java 25
- Spring Boot 4.1.1
- Spring Web MVC
- Spring Data JPA
- Thymeleaf
- Hibernate
- H2 Database
- Maven

## Project Structure

```text
student-manager/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/student_manager/
│   │   │       ├── controller/
│   │   │       ├── model/
│   │   │       ├── repository/
│   │   │       ├── service/
│   │   │       └── StudentManagerApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── templates/
│   └── test/
│       └── java/
├── data/
├── pom.xml
├── mvnw
├── mvnw.cmd
└── .mvn/
```

## Prerequisites

- JDK 25 or later
- Maven 3.9+ (or use the included Maven wrapper)

## Getting Started

From the project root:

```bash
cd student-manager
./mvnw clean install
./mvnw spring-boot:run
```

On Windows PowerShell or Command Prompt:

```powershell
cd student-manager
mvnw.cmd clean install
mvnw.cmd spring-boot:run
```

The application will start on:

- Application: http://localhost:8080/students
- H2 Console: http://localhost:8080/h2-console

## Database Configuration

The project uses an embedded H2 database stored in the local `data` folder.

Configuration in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:h2:file:./data/studentdb
spring.datasource.username=sa
spring.datasource.password=

spring.h2.console.enabled=true
spring.h2.console.path=/h2-console
```

For the H2 console login:

- JDBC URL: `jdbc:h2:file:./data/studentdb`
- Username: `sa`
- Password: leave empty

## Application Behavior

The app supports the following student fields:

- Full name
- Email
- Phone number
- Course
- Age

Validation rules include:

- Name is required and limited to 100 characters
- Email must be valid and unique
- Phone number must be exactly 10 digits
- Course must be selected
- Age must be between 15 and 100

## Notes

This project is designed as a simple CRUD-based student management system and is suitable for learning Spring Boot MVC, JPA, and Thymeleaf integration.
