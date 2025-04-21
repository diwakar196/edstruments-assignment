# Product Management REST API

This is a simple Spring Boot application that provides a RESTful API for managing a list of products.

## Features

- Create, read, update, delete (CRUD) products
- Input validation
- Exception handling

## Product Fields

- id (Long, auto-generated)
- name (String, required)
- description (String)
- price (Decimal, must be positive)

## How to Run

1. Make sure you have Java 17+ and Maven installed.
2. Clone the project.
3. Run the application using: ```mvn spring-boot:run```
4. The API will be available at `http://localhost:8080`.

## Validation Rules

1. name: must not be null or empty
2. price: must be a positive number

## Exception Handling

1. Returns 404 Not Found if product is not found
2. Returns 400 Bad Request if input validation fails

## Testing curL's

```bash
curl -X GET http://localhost:8080/api/products

curl -X GET http://localhost:8080/api/products/1

curl -X POST http://localhost:8080/api/products \
  -H "Content-Type: application/json" \
  -d '{"name": "Phone", "description": "Smartphone", "price": 699.99}'

curl -X PUT http://localhost:8080/api/products/1 \
  -H "Content-Type: application/json" \
  -d '{"name": "Updated Phone", "description": "New model", "price": 799.99}'

curl -X DELETE http://localhost:8080/api/products/1