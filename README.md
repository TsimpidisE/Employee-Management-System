# Employee Management System

A Spring Boot application providing a RESTful API for managing employees, departments, and roles in an organization. Demonstrates core Spring Boot concepts such as Spring Web, Spring Data JPA, validation, and error handling.

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## Features
- CRUD operations for Employees, Departments, and Roles
- Validation of request payloads
- Global exception handling with meaningful error responses
- Pagination and sorting support for list endpoints
- In-memory H2 database with easy switch to MySQL

## Project Structure

```
Employee-Management-System/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/tsimpidise/ems/
│   │   │       ├── config/         # Configuration classes (Swagger, CORS)
│   │   │       ├── controller/     # REST controllers for Employees, Departments, Roles
│   │   │       ├── dto/            # Data Transfer Objects for API payloads
│   │   │       ├── exception/      # Custom exceptions and global handlers
│   │   │       ├── model/          # JPA entities (Employee, Department, Role)
│   │   │       ├── repository/     # Spring Data JPA repositories
│   │   │       └── service/        # Business logic and transaction management
│   │   └── resources/
│   │       ├── application.properties  # DB configs, app settings
│   │       └── data.sql                # Sample seed data
│   └── test/
│       └── java/
│           └── com/tsimpidise/ems/      # Unit and integration tests
├── mvnw                                  # Maven wrapper
├── pom.xml                               # Maven build and dependencies
└── README.md                             # Project documentation
```

## Prerequisites
- Java 8 or higher
- Maven 3.6+
- (Optional) MySQL database if switching from H2

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/TsimpidisE/Employee-Management-System.git
   cd Employee-Management-System
   ```
2. Build the project:
   ```bash
   ./mvnw clean install
   ```

## Configuration
By default, the application uses an in-memory H2 database. To switch to MySQL:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/ems_db
spring.datasource.username=<your-username>
spring.datasource.password=<your-password>
spring.jpa.hibernate.ddl-auto=update
```

## Usage
Run the application:
```bash
./mvnw spring-boot:run
```
API available at `http://localhost:8080/api`.

## API Endpoints
| Method | Endpoint              | Description                 |
| ------ | --------------------- | --------------------------- |
| GET    | /api/employees        | List all employees          |
| POST   | /api/employees        | Create a new employee       |
| GET    | /api/employees/{id}   | Get employee by ID          |
| PUT    | /api/employees/{id}   | Update employee details     |
| DELETE | /api/employees/{id}   | Delete an employee          |
| GET    | /api/departments      | List all departments        |
| POST   | /api/departments      | Create a new department     |
| GET    | /api/roles            | List all roles              |
| POST   | /api/roles            | Create a new role           |

## Contributing
Contributions are welcome! Fork the repo and submit pull requests.

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Author
Efthymios Tsimpidis  
GitHub: https://github.com/TsimpidisE
