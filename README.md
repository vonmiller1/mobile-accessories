# Mobile Accessories Sales Server

A robust backend service for managing a mobile accessories sales operation using Java and Spring Boot. The system supports branch management, product catalog operations, customer records, sales agents, stock control, stock requests, and order processing through a REST API.

## Overview

This project provides a scalable server-side solution for a mobile accessories retail business. It exposes REST endpoints for managing inventory and sales-related workflows, including tracking stock movement, creating orders, updating request status, and retrieving sales summaries by branch and sales agent.

## Features

- Product catalog management
- Branch and sales outlet administration
- Customer management
- Sales agent tracking
- Inventory and stock monitoring
- Stock request workflow and status updates
- Order creation and sale analytics
- RESTful API design with standardized response models
- MySQL-backed persistence
- Validation and centralized exception handling

## Tech Stack

- Java 11
- Spring Boot 2.6.4
- Spring Web
- Spring Validation
- Spring Data JDBC
- MySQL Driver
- Maven
- Lombok

## Project Structure

```text
mobile-accessories/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/icbt/ap/mobileaccessoriessales/
│   │   │       ├── config/
│   │   │       ├── constant/
│   │   │       ├── controller/
│   │   │       ├── dto/
│   │   │       ├── entity/
│   │   │       ├── enums/
│   │   │       ├── exception/
│   │   │       ├── repository/
│   │   │       ├── service/
│   │   │       └── util/
│   │   └── resources/
│   │       ├── application.properties
│   │       └── messages/
│   └── test/
│       └── java/
├── pom.xml
├── mvnw
├── mvnw.cmd
├── README.md
└── .gitignore
```

## Core Modules

The backend includes the following domain areas:

- Branch management
- Customer management
- Product catalog
- Sales agents
- Vehicle handling
- Stock management
- Stock request processing
- Order and sales analytics

## API Base URL

The application is configured with a context path of `/api` and versioned routes under `/v1`.

Example base URL:

```text
http://localhost:8080/api/v1
```

## Prerequisites

Before running the application, ensure you have:

- Java 11 or newer
- Maven 3.8+
- MySQL 8.0 or compatible version
- A MySQL database named `sales_db`

## Configuration

Update the database connection settings in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/sales_db?useSSL=false
spring.datasource.username=root
spring.datasource.password=your_password
```

You may also need to adjust the Hibernate and server settings according to your local environment.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/vonmiller1/mobile-accessories.git
cd mobile-accessories
```

### 2. Configure MySQL

Create the database and ensure the credentials match your local MySQL setup.

```sql
CREATE DATABASE sales_db;
```

### 3. Build the project

```bash
./mvnw clean package
```

### 4. Run the application

```bash
./mvnw spring-boot:run
```

Once started, the API will be available on:

```text
http://localhost:8080/api
```

## Example Endpoints

The project exposes endpoints for major business operations, such as:

- `/api/v1/branch`
- `/api/v1/product`
- `/api/v1/customer`
- `/api/v1/user`
- `/api/v1/sales_agent`
- `/api/v1/stock`
- `/api/v1/stock-request`
- `/api/v1/orders`

## Testing

Run the test suite with:

```bash
./mvnw test
```

## Notes

This is a backend-only application. It is designed to support a frontend application or external client that consumes the REST API for mobile accessories sales operations.

## License

This project does not currently declare a specific license. If you intend to distribute or commercialize it, confirm the appropriate licensing terms before publishing.

## Contact

For project questions or support, contact the repository owner or maintainers through the GitHub project page.
