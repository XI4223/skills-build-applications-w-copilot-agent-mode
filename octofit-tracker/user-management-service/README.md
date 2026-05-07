# OctoFit Tracker - User Management Service

A Java Spring Boot microservice for managing OctoFit Tracker user profiles.

## Technology Stack

- **Java 17**
- **Spring Boot 3.2.5**
- **Spring Data JPA**
- **H2 In-Memory Database** (development/testing)
- **Maven**

## Getting Started

### Prerequisites

- Java 17+
- Maven 3.6+

### Build

```bash
cd octofit-tracker/user-management-service
mvn clean package
```

### Run

```bash
mvn spring-boot:run
```

The service starts on **port 8080** by default.

## REST API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/users` | Get all users |
| `GET` | `/api/users/{id}` | Get a user by ID |
| `GET` | `/api/users/username/{username}` | Get a user by username |
| `POST` | `/api/users` | Create a new user |
| `PUT` | `/api/users/{id}` | Update a user |
| `DELETE` | `/api/users/{id}` | Delete a user |

## Example Usage

### Create a User

```bash
curl -X POST http://localhost:8080/api/users \
  -H "Content-Type: application/json" \
  -d '{
    "username": "johndoe",
    "email": "john@example.com",
    "password": "password123",
    "firstName": "John",
    "lastName": "Doe"
  }'
```

### Get All Users

```bash
curl http://localhost:8080/api/users
```

### Get a User by ID

```bash
curl http://localhost:8080/api/users/1
```

### Update a User

```bash
curl -X PUT http://localhost:8080/api/users/1 \
  -H "Content-Type: application/json" \
  -d '{
    "username": "johndoe",
    "email": "john.updated@example.com",
    "password": "newpassword",
    "firstName": "John",
    "lastName": "Doe"
  }'
```

### Delete a User

```bash
curl -X DELETE http://localhost:8080/api/users/1
```

## H2 Console

During development, the H2 in-memory database console is available at:

```
http://localhost:8080/h2-console
```

- **JDBC URL**: `jdbc:h2:mem:octofit_users`
- **Username**: `sa`
- **Password**: *(empty)*

## Running Tests

```bash
mvn test
```
