# 💳 E-Banking System (Full Stack)

This is a **full-stack digital banking application** built with **Spring Boot (Java)** on the backend and **Angular** on the frontend.

---

## 🚀 Features

### 🔐 Authentication & Authorization

- Login with JWT-based authentication
- Role-based access control using scopes (`USER`, `ADMIN`)
- Protected routes using Angular Guards and Interceptors

### 👥 Customer Management

- View all customers
- Add, update, delete customers
- Search customers by keyword

### 💰 Account Operations

- View bank accounts (current/saving)
- Credit & debit account balances
- Transfer between accounts
- View transaction history (with pagination)

---

## 🧱 Tech Stack

| Layer    | Technology                    |
| -------- | ----------------------------- |
| Frontend | Angular 17+                   |
| Backend  | Spring Boot, Spring Security  |
| Auth     | JWT, Interceptor, Route Guard |
| Database | H2 / MySQL                    |
| Docs     | Swagger UI                    |
| Build    | Maven                         |
| Language | Java 17+, TypeScript          |

---

## 📦 Project Structure

### Backend: `ebanking-backend/`

```
├── config/             # Spring Security config
├── controllers/        # REST APIs
├── services/           # Business logic
├── entities/           # JPA entities
├── dtos/               # Data Transfer Objects
├── repositories/       # Spring Data JPA
├── mappers/            # DTO ↔ Entity conversion
├── exceptions/         # Custom exceptions
└── resources/          # application.properties etc.
```

### Frontend: `ebanking-frontend/`

```
├── app/
│   ├── services/           # Auth + HTTP services
│   ├── guards/             # Route guards (canActivate)
│   ├── interceptors/       # HTTP Interceptor for Bearer token
│   ├── login/              # Login page
│   ├── customers/          # Customers view
│   ├── accounts/           # Accounts view
│   ├── new-customer/       # Add customer form
│   └── admin-template/     # Shell layout (navbar + router-outlet)
```

---

## 🔑 Authentication Flow

- On successful login, backend returns a JWT token
- Token is saved to `localStorage`
- Angular interceptor adds `Authorization: Bearer <token>` to all HTTP requests
- Route guard (`canActivate`) protects `/admin` routes

---

## 📬 Key Backend Endpoints

| Method   | Endpoint                        | Description              |
| -------- | ------------------------------- | ------------------------ |
| `GET`    | `/customers`                    | List all customers       |
| `GET`    | `/customers/search?keyword=xyz` | Search customers by name |
| `POST`   | `/customers`                    | Create new customer      |
| `PUT`    | `/customers/{id}`               | Update existing customer |
| `DELETE` | `/customers/{id}`               | Delete customer          |
| `GET`    | `/accounts/{id}`                | View account details     |
| `POST`   | `/accounts/debit`               | Debit account            |
| `POST`   | `/accounts/credit`              | Credit account           |
| `POST`   | `/accounts/transfer`            | Transfer funds           |

> 🔐 All endpoints are secured using Spring Security + JWT scopes.

---

## ▶️ Run Backend

```bash
cd ebanking-backend
./mvnw spring-boot:run
```

### 🧪 Access Swagger UI:

[http://localhost:8085/swagger-ui.html](http://localhost:8085/swagger-ui.html)

---

## ▶️ Run Frontend

```bash
cd ebanking-frontend
npm install
ng serve
```

App will run at: [http://localhost:4200](http://localhost:4200)

---

## 👤 Author

**Mohamed Abiaba**\

---

