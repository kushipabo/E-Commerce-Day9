# 💼 Employee Management System (Spring Boot)

A RESTful Spring Boot application tailored for managing organizational departments, with a modular structure and clean architecture. The current version focuses on **department management**, with employee features planned for future development.

---

## 📖 Overview

This project demonstrates how to implement CRUD operations for departments using a RESTful API in Spring Boot. It follows a layered architecture to separate concerns and ensure maintainability. While the `Employee` entity is referenced, its implementation is **not yet included**.

---

## 🏗️ Application Architecture

The application uses a **4-layered architecture**:

### 🔸 Model Layer

#### `Department.java`
Represents the department entity.

- Fields:
  - `id (Long)` – Primary key
  - `name (String)` – Department name
  - `establishedDate (Date)` – Date of creation
  - `employees (List<Employee>)` – One-to-Many (planned feature)

#### `Employee.java` *(Planned)*
- Placeholder for future functionality.
- Will be associated with departments.

---

### 🔸 Repository Layer

#### `DepartmentRepo`
- Interface extending `JpaRepository<Department, Long>`
- Provides all standard CRUD operations via Spring Data JPA

---

### 🔸 Service Layer

#### `DepartmentService`
Encapsulates business logic for:

- Retrieving all departments
- Fetching a department by ID

Ensures a clean separation between the controller and repository layers.

---

### 🔸 Controller Layer

#### `DepartmentController`
REST API entry point for department operations.

- `GET /dept` – Retrieve all departments
- `GET /dept/{id}` – Retrieve a department by its ID

> 🚧 **Commented-out stubs included for:**
> - `POST` – Create department  
> - `PUT` – Update department  
> - `DELETE` – Delete department  

---

## 🗃️ Database Configuration

Ensure MySQL is installed and running.

Update `application.properties` in `src/main/resources/`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/employee
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
