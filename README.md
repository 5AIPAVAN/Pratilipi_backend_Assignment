# Personalized Notification System

A microservices-based personalized notification system designed for an e-commerce platform. This system enables real-time, personalized notifications for users based on their preferences and activity.

## 📌 Overview
This project follows a **microservices architecture**, ensuring scalability and flexibility. It consists of the following core services:

- **User Service** → Manages user authentication, preferences, and profiles.
- **Notification Service** → Handles storage, delivery, and status of notifications.
- **Scheduler Service** → Triggers notifications at scheduled intervals.
- **Recommendation Service** → Generates personalized product recommendations.
- **GraphQL Gateway** → Acts as a unified API gateway for seamless data fetching.

### 🔧 Tech Stack
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Messaging Queue**: RabbitMQ
- **Caching & Session Management**: Redis
- **Monitoring**: Prometheus, Grafana

## 🚀 Getting Started

### Prerequisites
Ensure you have the following installed:
- Docker & Docker Compose
- Git
- Node.js (for local development)

### 📥 Clone the Repository
```bash
git clone https://github.com/5AIPAVAN/Pratilipi_backend_Assignment.git
cd Pratilipi_backend_Assignment
```

### 🏗 Start All Services
Run the following command to start all microservices:
```bash
docker-compose up -d
```
Check the status of running services:
```bash
docker-compose ps
```

## 🌐 Service Endpoints

| Service                  | URL                            | Description                  |
|--------------------------|--------------------------------|------------------------------|
| **GraphQL Gateway**      | http://localhost:5000/graphql | Unified API Gateway          |
| **User Service**         | http://localhost:4001         | User management API          |
| **Notification Service** | http://localhost:4002         | Handles notifications        |
| **Recommendation Service** | http://localhost:4003      | Generates recommendations    |
| **MongoDB**              | localhost:27017               | NoSQL Database               |
| **RabbitMQ Management**  | http://localhost:15672        | Message broker dashboard     |
| **Redis**                | localhost:6379                | Caching system               |
| **Prometheus**           | http://localhost:9090         | Metrics collection           |
| **Grafana**              | http://localhost:3000         | Monitoring dashboards        |

## 📌 Backend Intern Assignment - Problem Statement
You are required to develop a **Personalized Notification System** for an e-commerce platform. This system should be capable of sending tailored notifications to users based on their preferences and interactions.

### System Breakdown
1. **User Service**
   - Register a user (Name, Email, Preferences).
   - Update user preferences (e.g., preferred notification types: promotions, order updates, recommendations).
   - Fetch user details.

2. **Notification Service**
   - Store notifications with attributes:
     - `id`: Unique identifier
     - `userId`: Target user ID
     - `type`: Notification type (promotion, order update, recommendation)
     - `content`: Notification message (text/JSON)
     - `sentAt`: Timestamp
     - `read`: Boolean status
   - Mark notifications as read.
   - Fetch unread notifications for a user.

3. **Personalized Notifications**
   - Generate recommendations using:
     - Purchase history (mock data)
     - Browsing activity (mock data)
   - Store recommendations and send notifications.

4. **Scheduled Notifications**
   - Use a scheduler (e.g., Cron jobs) to:
     - Send order status updates.
     - Push promotional notifications to users based on preferences.

5. **Message Queue Integration**
   - Use RabbitMQ/Kafka for:
     - Handling high-throughput user activity events.
     - Managing asynchronous event-driven communication between services.
     - Ensuring state consistency across microservices.

6. **GraphQL Gateway**
   - Implement a **GraphQL API Gateway** to unify all microservices.
   - Ensure no microservices are directly exposed to the client.

### 🎯 Requirements
- **Asynchronous Communication**: Use queue/streaming for inter-service communication.
- **GraphQL API**: Acts as a single point of interaction for the client.
- **Database Management**: Assign services to respective databases.
- **Queue/Stream-Based State Management**: Services should listen to relevant events and update their local state.
- **Authentication**: JWT-based authentication in the User Service.

### 🛠 Development
#### 🏗 Rebuild Individual Services
```bash
docker-compose build service-name
docker-compose up -d service-name
```
#### 📜 Viewing Logs
```bash
docker-compose logs -f  # Logs for all services
docker-compose logs -f service-name  # Logs for a specific service
```
#### 🔍 Monitoring
- **Prometheus**: [http://localhost:9090](http://localhost:9090)
- **Grafana**: [http://localhost:3000](http://localhost:3000)
  - Log in and add Prometheus as a data source (`http://prometheus:9090`).
  - Import dashboards for RabbitMQ and other metrics.

### 📌 Scaling Services
To scale a service dynamically:
```bash
docker-compose up -d --scale service-name=3
```
### 🛑 Stopping Services
```bash
docker-compose down  # Stop all services
docker-compose down -v  # Stop and remove volumes
```

## 📌 Testing Scheduler Service
The scheduler triggers recommendation and promotion notifications **every 10 seconds**, so you will see new notifications frequently.

## 🎯 Bonus Features
- **Caching**: Implement caching in GraphQL for frequently queried data.
- **Message Queue Monitoring**: Monitor RabbitMQ/Kafka using Prometheus & Grafana.
- **Dead Letter Queues**: Handle failed event deliveries.
- **Unit Tests**: Use Jest/Mocha for testing microservices.

## 📌 Submission Guidelines
- Provide **detailed README files** for each microservice.
- **Explain the entire architecture** clearly.
- Include **Docker configurations** for microservices, GraphQL server, databases, and queues.
- Submit **Postman collections** or **GraphQL playground queries** for testing.

## 🚀 Conclusion
This project aims to provide a **scalable, event-driven, and personalized notification system** for an e-commerce platform. The open-ended nature allows for innovation in design and implementation. Looking forward to seeing how you approach this challenge! 🎉
