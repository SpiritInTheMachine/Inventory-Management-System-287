# Web-Based Inventory Management System

## Overview
The **Web-Based Inventory Management System** is a full-stack application designed to streamline inventory management for businesses. It allows users to manage products, parts, and purchases efficiently while ensuring that inventory constraints are maintained. The system offers real-time inventory tracking, purchasing functionality, validation checks, and user-friendly navigation.

This project demonstrates proficiency in **Java**, **Spring Boot**, **Hibernate (JPA)**, and modern web development tools. The application includes robust backend logic, effective frontend design, and unit-tested features, showcasing key software engineering and full-stack development skills.

---

## Features
- **CRUD Operations:**
  - Add, update, delete, and manage parts and products.
  - Track inventory levels for each product and part.

- **Inventory Constraints:**
  - Minimum and maximum inventory validation.
  - Prevent actions that cause inventory to fall below or exceed constraints.

- **Purchasing Functionality:**
  - "Buy Now" button reduces product stock dynamically without affecting associated parts.
  - Success and failure messages based on stock availability.

- **User-Friendly Navigation:**
  - Clean, responsive UI built with Bootstrap and Thymeleaf.
  - Navigation buttons allow seamless switching between key pages (e.g., main screen, "About" page).

- **Localization Support:**
  - Multi-language support with resource bundles for English (`en_US`) and French (`fr_CA`).

- **Unit Testing:**
  - JUnit tests validate key inventory fields (`minInv` and `maxInv`) to ensure data integrity.

---

## Technologies Used

### **Backend:**
- **Java**: Core programming language used for the business logic.
- **Spring Boot**: Framework for building the backend, RESTful APIs, and dependency injection.
- **Hibernate (JPA)**: ORM tool for database operations.
- **H2 Database**: Lightweight, in-memory database used during development.

### **Frontend:**
- **HTML & CSS**: Core web technologies for structuring and styling the UI.
- **Bootstrap**: Responsive design and pre-styled UI components.
- **Thymeleaf**: Template engine for rendering dynamic HTML pages.

### **Development Tools:**
- **IntelliJ IDEA**: Primary IDE for coding and debugging.
- **Git & GitLab**: Version control and project repository.
- **JUnit**: Unit testing framework for ensuring code reliability.

---

## How to Run the Project

### **Prerequisites:**
- Java Development Kit (JDK) 11+
- IntelliJ IDEA (or your preferred IDE)
- Maven (for dependency management)

### **Steps to Run Locally:**
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd inventory-management-system
   ```
3. Open the project in IntelliJ IDEA.
4. Build the project using Maven:
   ```bash
   mvn clean install
   ```
5. Run the Spring Boot application:
   ```bash
   mvn spring-boot:run
   ```
6. Access the application at:
   ```
   http://localhost:8080/
   ```

---

## Project Structure

- **`src/main/java/com/example/demo`**: Contains the Java source code.
  - **Controllers**: Handle HTTP requests and manage application flow.
  - **Domain**: Contains core entities such as `Part` and `Product`.
  - **Repository**: Interfaces for data access using JPA.
  - **Service**: Business logic layer.
  - **Validators**: Custom validation logic.

- **`src/main/resources`**:
  - **Templates**: Thymeleaf HTML files for frontend rendering.
  - **Static Resources**: CSS, JavaScript, and image files.
  - **Localization**: `Translate_en_US.properties` and `Translate_fr_CA.properties` files for multi-language support.

---

## Sample Functionalities (Key Code Highlights)

### **Adding Parts and Products:**
- Forms allow users to input product/part details and enforce validation.
- Controller logic ensures inventory stays within allowed constraints (min/max).

### **Sample Inventory:**
- Automatically adds five parts and five products when the system is first run (if the database is empty).
- Duplicate parts are managed using "multi-pack" parts.

### **Validation Example:**
- Error messages are displayed if inventory is below the minimum or exceeds the maximum.
  - Example: "Inventory cannot be lower than the minimum value."

### **Buy Now Button:**
- Decrements the product inventory by one and displays success or failure messages based on stock availability.

---

## Unit Testing

The project includes unit tests to ensure data integrity and correct functionality.

- **Test File:** `PartTest.java`
  - Tests for `minInv` and `maxInv` fields to verify inventory constraints.
  - Example Test:
    ```java
    @Test
    void testMinInventory() {
        Part part = new InhousePart();
        part.setMinInv(5);
        assertEquals(5, part.getMinInv());
    }
    ```

---

## Future Enhancements
- Add more detailed error handling and validation.
- Implement advanced reporting and inventory analytics.
- Integrate RESTful API for external system integration.

---
