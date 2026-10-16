# Mobile Accessories Sales Server

REST backend for managing sales and inventory operations for a mobile accessories business. Built with Java and Spring Boot, it provides endpoints for products, branches, customers, users, sales agents, stock, stock requests, and orders.

## Features

- Manage product, branch, customer, and user records
- Track stock and process stock requests
- Manage orders and update order statuses
- Retrieve order totals grouped by sales agent
- Validate API input and return consistent response objects
- Persist application data in MySQL

## Technology

- Java 11
- Spring Boot 2.6.4
- Spring Web, Validation, and Data JDBC
- MySQL
- Maven Wrapper
- Lombok

## Requirements

- Java 11 or later
- MySQL

The repository includes Maven Wrapper scripts, so a separate Maven installation is not required.

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/vonmiller1/mobile-accessories.git
cd mobile-accessories
```

### 2. Create a database

Create the database configured for the application:

```sql
CREATE DATABASE sales_db;
```

### 3. Configure the database connection

Set the MySQL URL, username, and password in `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/sales_db?useSSL=false
spring.datasource.username=root
spring.datasource.password=your_password
```

Replace `your_password` with the password for your local MySQL account. Avoid committing real credentials; use environment-specific configuration for shared or production deployments.

### 4. Run the application

On Windows:

```powershell
.\mvnw.cmd spring-boot:run
```

On macOS or Linux:

```bash
./mvnw spring-boot:run
```

The server starts at `http://localhost:8080` with the `/api` context path.

## API

Version 1 endpoints are available under:

```text
http://localhost:8080/api/v1
```

The main resource paths include:

| Resource | Endpoint |
| --- | --- |
| Branches | `/api/v1/branch` |
| Products | `/api/v1/product` |
| Customers | `/api/v1/customer` |
| Users | `/api/v1/user` |
| Sales agents | `/api/v1/sales_agent` |
| Stock | `/api/v1/stock` |
| Stock requests | `/api/v1/stock-request` |
| Orders and sales totals | `/api/v1/orders` |

For example, the orders API provides order results, totals by sales agent, and an endpoint for updating an order's status. See the controllers under `src/main/java/com/icbt/ap/mobileaccessoriessales/controller` for supported methods and request/response details.

## Build and test

Run the test suite:

```powershell
.\mvnw.cmd test
```

On macOS or Linux, use `./mvnw test`. To build the deployable artifact, run `.\mvnw.cmd clean package` on Windows or `./mvnw clean package` on macOS and Linux.

## Project layout

```text
src/
├── main/
│   ├── java/com/icbt/ap/mobileaccessoriessales/
│   │   ├── controller/   REST API controllers
│   │   ├── dto/          API response objects
│   │   ├── entity/       Domain and query models
│   │   ├── repository/   Data access
│   │   ├── service/      Business logic
│   │   └── ...
│   └── resources/        Application and message configuration
└── test/                 Automated tests
```

## License

No license is currently specified in this repository. All rights remain with the respective copyright holders unless a license is added.
