

# Rule Engine with AST

## Overview

The **Rule Engine with AST** is a dynamic engine that allows users to create, combine, and evaluate rules using an Abstract Syntax Tree (AST) structure. The engine supports evaluating conditions like age, department, salary, etc., and combines rules using logical operators (AND/OR). Rules are stored in a MySQL database, and Spring Boot is used to manage the backend operations.

## Features

- Create and evaluate rules using an AST (Abstract Syntax Tree) structure.
- Combine rules with logical operators (AND/OR).
- Evaluate conditions such as age, department, salary, and more.
- Store and manage rules in a MySQL database.
- Easily extendable to support more complex rules and operators.

## Technologies Used

- **Java 17**
- **Spring Boot 3.3.4**
- **Spring Data JPA**
- **MySQL**
- **Lombok** (to reduce boilerplate code)

## How to Run

1. **Clone this repository:**

   ```bash
   git clone https://github.com/Aryan13242/Rule_Engine_with_AST.git
   ```

2. **Set up MySQL and create a database:**

   ```sql
   CREATE DATABASE rule_engine_db;
   ```

3. **Update the `application.properties` file** located in `src/main/resources` with your MySQL credentials:

   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/rule_engine_db
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   ```

4. **Run the application:**

   ```bash
   mvn spring-boot:run
   ```

5. The application will be available at:  
   **http://localhost:8080**

## API Endpoints

### 1. Create Rule

- **Endpoint:** `POST /api/rules/create`
- **Request Body:** A raw rule string (e.g., `"(age > 30 AND department = 'Sales')"`).
- **Response:** The AST representation of the rule.

### 2. Combine Rules

- **Endpoint:** `POST /api/rules/combine`
- **Request Body:** Two rules and a logical operator (AND/OR).
- **Response:** The combined rule in AST format.

### 3. Evaluate Rule

- **Endpoint:** `POST /api/rules/evaluate`
- **Request Body:** Rule and user data (e.g., age, department).
- **Response:** `True`/`False` based on the rule evaluation.

## Future Improvements

- Add support for more complex logical operators and data types.
- Implement a user-friendly interface to easily manage and visualize rules.
- Add more dynamic validation and error handling during rule creation and evaluation.
