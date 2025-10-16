# 🎨 Book Store full presentation

the link below:

👉 [Open the Design in Canva](https://www.canva.com/design/DAG1y0lcp30/jQPA-sxWVKTto5IEVCcRcg/edit?utm_content=DAG1y0lcp30&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)


# 📚 Book Store — Microservices Architecture

## 🧩 Overview
The **Book Store** project is a microservices-based system that simulates a complete online book store platform.  
It demonstrates how multiple independent services can collaborate through APIs and asynchronous messaging to create a scalable, maintainable, and production-ready system.

This project emphasizes backend architecture, containerization, and inter-service communication while maintaining a functional frontend for user interaction.

---

## 🏗️ Architecture
The system is composed of several microservices, each responsible for a distinct functionality:

| Service | Technology Stack | Database | Description |
|----------|------------------|-----------|--------------|
| **User Service** | Node.js | MongoDB | Handles user registration, login, authentication, and profile management. |
| **Book Service** | Spring Boot | MySQL | Manages book data — titles, authors, categories, and availability. |
| **Order Service** | Spring Boot | PostgreSQL | Manages customer orders and order history. |
| **Payment Service** | Spring Boot | PostgreSQL | Handles secure payment processing. |
| **Notification Service** | Node.js | — | Sends real-time email notifications using RabbitMQ as a message broker. |
| **API Gateway Service** | Node.js | — | Routes and authenticates API calls between frontend and backend microservices. |

Additionally, **RabbitMQ** is used for asynchronous communication between microservices, ensuring decoupled and efficient event-driven operations.

Each microservice runs inside a dedicated **Docker container**, simplifying setup and deployment.

---

## 🎨 Frontend
A minimal, responsive interface built using:
- HTML
- CSS
- JavaScript  

The focus is on backend communication rather than complex UI, allowing seamless interaction with backend APIs.

---

## 🗂️ Project Structure

To run the entire system, organize the repositories as follows:

BookStore/
│
├── user-service/
├── book-service/
├── order-service/
├── payment-service/
├── notification-service/
├── api-gateway-service/
├── docker-compose.yml

yaml
Copy code

> Each folder corresponds to a separate microservice repository (all available in our GitHub organization).

---

## ⚙️ Setup & Run Instructions

### 1️⃣ Clone All Repositories
Create a new folder and name it `BookStore`:

```bash
mkdir BookStore
cd BookStore
Then clone each microservice repository inside this folder:

bash
Copy code
git clone <user-service-repo-url>
git clone <book-service-repo-url>
git clone <order-service-repo-url>
git clone <payment-service-repo-url>
git clone <notification-service-repo-url>
git clone <api-gateway-service-repo-url>

2️⃣ Add docker-compose.yml
Place the docker-compose.yml file inside the root BookStore directory.

3️⃣ Build and Run Containers
Make sure Docker is installed and running, then execute:

Copy code
docker compose up --build

This will:

Build and run all microservices in separate containers.

Automatically connect them through Docker networks.

Start the RabbitMQ broker for message handling.

🔒 Authentication & Communication
Each request is authenticated using JWT tokens.

The token is verified by every service upon API call.

The API Gateway manages routing and token validation.

RabbitMQ handles message-based communication between user-service, book-service, order-service, and notification-service.

✉️ Notifications
The notification-service listens to message events via RabbitMQ and sends:

Login confirmation emails

Order confirmation emails

🐳 Docker & Deployment
Each microservice includes its own Dockerfile.
Containerization ensures:

Isolated environments

Easy scalability

Portability across different systems

Example command to list running containers:


Copy code
docker ps

🌐 Access
Once all services are running:

API Gateway will be accessible on its configured port (e.g., http://localhost:8080)

Frontend files can be opened in a browser (or served through a static file server).

💡 Technologies Used
Node.js

Spring Boot

MongoDB, MySQL, PostgreSQL

RabbitMQ

Docker, Docker Compose

HTML, CSS, JavaScript

🤝 Team & Organization
This project is hosted under our dedicated GitHub Organization, which contains all individual microservice repositories.
You can check it out and explore each service independently.

🚀 Future Enhancements
Add frontend framework (React or Angular)

Implement API documentation using Swagger

Introduce centralized logging and monitoring

Deploy to a cloud platform using CI/CD pipelines

🏁 Conclusion
The Book Store Microservices Project is a hands-on implementation of modern backend architecture principles, emphasizing modularity, scalability, and asynchronous communication.

It provided our team with practical experience in:

Designing and integrating distributed systems

Using Docker for microservice orchestration

Implementing event-driven patterns using RabbitMQ

Managing secure communication between services

💬 Feel free to explore the repos and try it yourself!
