# 🧠 Quiz Management System — Microservices Architecture

A modular, scalable **Quiz Management System** built with Spring Boot Microservices and React. It uses **Eureka Service Registry** for service discovery and **API Gateway** for routing and security.

---

## ⚙️ Microservices Architecture

```
                +-------------------+
                |   React Frontend  |
                +--------+----------+
                         |
                         ▼
                +-------------------+
                |    API Gateway    |
                +--------+----------+
                         |
        +----------------+----------------+
        |                                 |
        ▼                                 ▼
+---------------+                +------------------+
|  Quiz Service |                | Question Service |
+---------------+                +------------------+
        \                                 /
         \                               /
          +-----------+   +------------+
                      ▼   ▼
               +-----------------+
               | Eureka Registry |
               +-----------------+
```

---

## 🛠️ Tech Stack

### 💻 Backend:
- Java + Spring Boot
- Spring Cloud Gateway (API Gateway)
- Eureka Server (Service Registry)
- Spring Web, Spring Data JPA
- MySQL / H2

### 🌐 Frontend:
- React.js
- Axios
- Tailwind CSS (optional)


---

## 🚀 Running the Application

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/quiz-microservice-app.git

```

---

### 2️⃣ Start Backend Services

> Open each terminal in a new tab or window.

#### ✅ Start Eureka Server

```bash
cd backend/eureka-server
./mvnw spring-boot:run
```

Visit: `http://localhost:8761` (Service registry dashboard)

---

#### ✅ Start API Gateway

```bash
cd backend/api-gateway
./mvnw spring-boot:run
```

Runs on: `http://localhost:8080`

---

#### ✅ Start Quiz Service

```bash
cd backend/quiz-service
./mvnw spring-boot:run
```

---

#### ✅ Start Question Service

```bash
cd backend/question-service
./mvnw spring-boot:run
```

> ✅ All services will auto-register to Eureka and communicate via the API Gateway.

---

### 3️⃣ Start Frontend (React)

```bash
cd frontend
npm install
npm start
```

Visit: `http://localhost:3000`

---

## 🔀 API Gateway Routing

| Endpoint                  | Service           |
|---------------------------|-------------------|
| `/quiz/**`               | Quiz Service      |
| `/question/**`           | Question Service  |

Gateway routes are defined in `application.properties` of `api-gateway`.

---

## 📖 Sample APIs

### ➕ Add Quiz

```http
POST /quiz/add
Content-Type: application/json

{
  "title": "Spring Boot Basics",
  "description": "Quiz on Spring Boot concepts"
}
```

### 🔍 Get All Quizzes

```http
GET /quiz/all
```

---

## ✨ Features

- CRUD operations on **Quizzes** and **Questions**
- Modular microservices
- Service discovery with **Eureka**
- Routing via **API Gateway**
- Frontend integration with **React**
- Ready for scaling and CI/CD

---


## 👨‍💻 Author

**Soumyakanta Rout**  
🔗 [LinkedIn](https://www.linkedin.com/in/soumyakanta-rout45)

---



## 💡 Future Improvements

- JWT-based Authentication
- Kafka Integration for events
- MongoDB for Question Service
- Deployment via Docker + Kubernetes
