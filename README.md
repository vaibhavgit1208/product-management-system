
# 📦 Product Management System

A **Spring Boot REST API** project for managing products. This system allows CRUD operations on products with fields like **name, category, price, and quantity**.
Built using **Spring Boot, Spring Data JPA (Hibernate), Lombok, and MySQL/H2**.

---

## ✨ Features

* ➕ **Add** new products
* 📋 **View** all products
* 🔍 **Get** product by ID
* ✏️ **Update** existing product
* ❌ **Delete** product
* ⚠️ **Exception handling** with proper error messages
* 🛡️ **Spring Security** config included (currently open for easy API testing)

---

## 🛠️ Tech Stack

* **Language:** Java 17
* **Framework:** Spring Boot 3.2.2
* **Database:** MySQL (primary) / H2 (testing)
* **ORM:** Spring Data JPA (Hibernate)
* **Security:** Spring Security
* **Utilities:** Lombok
* **Build Tool:** Maven

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/product-management-system.git
cd product-management-system
```

### 2. Configure the database

Create a MySQL database:

```sql
CREATE DATABASE productdb;
```

Update `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/productdb
spring.datasource.username=root
spring.datasource.password=yourpassword

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```

💡 **Tip:** For testing, H2 is included. Comment out MySQL configs and Spring Boot will use H2 in-memory DB.

### 3. Build & Run

```bash
mvn clean install
mvn spring-boot:run
```

The app will start at: [http://localhost:8080](http://localhost:8080)

---

## 📖 API Documentation

**Base URL:** `/api/products`

| Method | Endpoint             | Description          |
| ------ | -------------------- | -------------------- |
| POST   | `/api/products`      | Create a new product |
| GET    | `/api/products`      | Get all products     |
| GET    | `/api/products/{id}` | Get product by ID    |
| PUT    | `/api/products/{id}` | Update product by ID |
| DELETE | `/api/products/{id}` | Delete product by ID |

---

### 🔹 Example Requests

#### 1. Create Product

**POST** `/api/products`
**Request Body:**

```json
{
  "name": "Laptop",
  "category": "Electronics",
  "price": 75000,
  "quantity": 10
}
```

**Response:**

```json
{
  "id": 1,
  "name": "Laptop",
  "category": "Electronics",
  "price": 75000,
  "quantity": 10
}
```

#### 2. Get All Products

**GET** `/api/products`
**Response:**

```json
[
  {
    "id": 1,
    "name": "Laptop",
    "category": "Electronics",
    "price": 75000,
    "quantity": 10
  },
  {
    "id": 2,
    "name": "Phone",
    "category": "Electronics",
    "price": 30000,
    "quantity": 5
  }
]
```

#### 3. Get Product by ID

**GET** `/api/products/1`
**Response:**

```json
{
  "id": 1,
  "name": "Laptop",
  "category": "Electronics",
  "price": 75000,
  "quantity": 10
}
```

**If product not found:**

```json
{
  "timestamp": "2025-09-16T14:32:10.123",
  "message": "Product not found with id 99",
  "status": 404
}
```

#### 4. Update Product

**PUT** `/api/products/1`
**Request Body:**

```json
{
  "name": "Gaming Laptop",
  "category": "Electronics",
  "price": 95000,
  "quantity": 8
}
```

**Response:**

```json
{
  "id": 1,
  "name": "Gaming Laptop",
  "category": "Electronics",
  "price": 95000,
  "quantity": 8
}
```

#### 5. Delete Product

**DELETE** `/api/products/1`
**Response:**

```
Product deleted successfully!
```

---

## 🧪 Testing

Run tests using:

```bash
mvn test
```

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new branch (`feature/new-feature`)
3. Commit your changes
4. Push to your branch and open a Pull Request

---

## 📜 License

This project is licensed under the **MIT License**.


