# https-github.com-VinDeli-gameauth-api
A secure REST API authentication service built with Java and Dropwizard framework for managing game user authentication and authorization. This microservice provides role-based access control for gaming applications with comprehensive health monitoring and security features.

Game Authentication API
Course: CS 230: Operating Platforms
Author: Vinessa Deliberto
Repository: https://github.com/VinDeli/gameauth-api
📋 Project Overview
A secure REST API authentication service built with Java and Dropwizard framework for managing game user authentication and authorization. This microservice provides role-based access control for gaming applications with comprehensive health monitoring and security features.
🚀 Features

Secure Authentication: Basic credential authentication with custom authenticator
Role-Based Authorization: Granular permission control using custom authorizer
RESTful API Design: Clean, scalable endpoints for user management
Health Monitoring: Built-in health checks for API monitoring
Microservice Architecture: Lightweight, production-ready service design
Dependency Injection: Proper separation of concerns and testability

🛠️ Technology Stack

Framework: Dropwizard
REST API: Jersey (JAX-RS)
Build Tool: Maven
Language: Java 8+
Authentication: Basic HTTP Authentication
Security: Role-based access control
Monitoring: Health check endpoints

📁 Project Structure
gameauth/
├── src/main/java/com/gamingroom/gameauth/
│   ├── GameAuthApplication.java          # Main application entry point
│   ├── auth/
│   │   ├── GameAuthenticator.java        # User authentication logic
│   │   ├── GameAuthorizer.java           # Role-based authorization
│   │   └── GameUser.java                 # User model
│   ├── controller/
│   │   └── GameUserRESTController.java   # REST endpoints
│   ├── dao/
│   │   └── GameUserDB.java               # Data access layer
│   └── healthcheck/
│       ├── AppHealthCheck.java           # Application health monitoring
│       └── HealthCheckController.java    # Health check endpoints
└── pom.xml                               # Maven dependencies
🔧 Setup & Installation

Prerequisites
bashJava 8+ installed
Maven 3.6+ installed

Clone Repository
bashgit clone https://github.com/VinDeli/gameauth-api.git
cd gameauth-api

Build Project
bashmvn clean compile

Run Application
bashmvn exec:java -Dexec.mainClass="com.gamingroom.gameauth.GameAuthApplication"

Access API

Base URL: http://localhost:8080
Health Check: http://localhost:8081/healthcheck


Security Features
Authentication

Basic HTTP Authentication for secure user verification
Custom GameAuthenticator validates user credentials
Secure credential handling and validation

Authorization

Role-Based Access Control (RBAC) implementation
Custom GameAuthorizer manages user permissions
Fine-grained access control for different user roles

Security Configuration
java// Basic Security Setup
new BasicCredentialAuthFilter.Builder<GameUser>()
    .setAuthenticator(new GameAuthenticator())
    .setAuthorizer(new GameAuthorizer())
    .setRealm("App Security")
    .buildAuthFilter()
📊 API Endpoints
MethodEndpointDescriptionAuth RequiredGET/usersList all usersYesGET/users/{id}Get user by IDYesPOST/usersCreate new userAdminPUT/users/{id}Update userAdminDELETE/users/{id}Delete userAdminGET/healthHealth checkNo
🏥 Health Monitoring
The application includes comprehensive health monitoring:

API Health Check: Monitors core API functionality
Multiple Health Checks: Extensible health check system
Jersey Client Integration: External service monitoring capability

java// Health Check Registration
e.healthChecks().register("APIHealthCheck", new AppHealthCheck(client));
e.jersey().register(new HealthCheckController(e.healthChecks()));
🧪 Key Learning Outcomes
Technical Skills Developed

Dropwizard Framework: Microservice development with embedded Jetty
Jersey/JAX-RS: RESTful web service implementation
Security Implementation: Authentication and authorization patterns
Dependency Injection: Clean architecture and testable code
Health Monitoring: Production-ready application monitoring

Software Engineering Practices

Clean Code: Proper separation of concerns and maintainable structure
Security First: Built-in authentication and authorization from the ground up
Production Ready: Health checks and monitoring for deployment
Scalable Design: Microservice architecture for horizontal scaling

 Future Enhancements

 JWT token-based authentication
 Database integration for persistent user storage
 Unit and integration test coverage
 Docker containerization
 API documentation with Swagger/OpenAPI
 Rate limiting and throttling
 Audit logging for security events

📚 Dependencies
xml<dependencies>
    <dependency>
        <groupId>io.dropwizard</groupId>
        <artifactId>dropwizard-core</artifactId>
    </dependency>
    <dependency>
        <groupId>io.dropwizard</groupId>
        <artifactId>dropwizard-auth</artifactId>
    </dependency>
    <dependency>
        <groupId>io.dropwizard</groupId>
        <artifactId>dropwizard-client</artifactId>
    </dependency>
</dependencies>
  Contributing
This project was developed as part of CS 230: Operating Platforms coursework. For academic integrity, please refer to your institution's policies regarding code sharing and collaboration.
  License
This project is developed for educational purposes as part of Southern New Hampshire University coursework.

Repository Link: https://github.com/VinDeli/gameauth-api
Course: CS 230: Operating Platforms
Institution: Southern New Hampshire University
