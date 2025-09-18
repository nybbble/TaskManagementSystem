# TaskManagementSystem

task-management-system/
│── src/
│   └── main/
│       └── java/com/example/taskmanagement/
│           ├── controller/
│           │   └── TaskController.java
│           ├── model/
│           │   └── Task.java
│           ├── repository/
│           │   └── TaskRepository.java
│           ├── service/
│           │   └── TaskService.java
│           └── TaskManagementApplication.java
│   └── test/
│       └── java/com/example/taskmanagement/
│           └── TaskControllerTest.java
│
│── resources/
│   └── application.yml
│
│── .gitignore
│── Dockerfile
│── pom.xml
│── README.md

A simple **RESTful API** built with **Java Spring Boot + PostgreSQL** for managing tasks.

---

## 🚀 Features
- Create a new task
- Get all tasks
- Delete task by ID
- PostgreSQL database integration
- Dockerized for easy deployment

---

## 🛠️ Tech Stack
- Java 17
- Spring Boot 3
- PostgreSQL
- Docker

---

## ▶️ How to Run
### 1️⃣ Run PostgreSQL with Docker
```bash
docker run --name postgres -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=tasksdb -p 5432:5432 -d postgres

**## Build and Run Application**

mvn clean package -DskipTests
docker build -t task-management .
docker run -p 8080:8080 --name task-app --link postgres task-management


**📌 API Endpoints**

GET /api/tasks → List all tasks

POST /api/tasks → Create new task

DELETE /api/tasks/{id} → Delete task

**✅ Example Request**

curl -X POST http://localhost:8080/api/tasks \
-H "Content-Type: application/json" \
-d '{"title":"Finish project","description":"Complete GitHub plan","completed":false}'
