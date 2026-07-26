# nsws-backend-portfolio
Backend engineering portfolio reflecting my experience contributing to the National Single Window System (NSWS). Features Java, Spring Boot, REST APIs, Microservices, Hibernate/JPA, PostgreSQL, and enterprise application design using original documentation and sample code.

# Enterprise Single Window Platform (ESWP)

> A portfolio project inspired by enterprise-scale single window platforms used for business approvals, regulatory clearances, and application lifecycle management.

> **Disclaimer**
>
> This repository is an independently created portfolio project inspired by my experience developing enterprise backend applications using Java and Spring Boot. It does **not** contain proprietary source code, confidential business logic, or internal architecture from any employer or client.

---

# Overview

Enterprise Single Window Platform (ESWP) is a microservices-based backend system that enables businesses to submit applications, upload supporting documents, track approval workflows, receive notifications, and monitor application status through a unified digital platform.

The project demonstrates enterprise backend development using Java, Spring Boot, REST APIs, Microservices, PostgreSQL, Spring Security, Hibernate, JPA, and Maven.

---

# Technology Stack

- Java 8
- Spring Boot
- Spring MVC
- Spring Security
- Hibernate
- Spring Data JPA
- PostgreSQL
- Maven
- REST APIs
- JWT Authentication
- Docker
- Kubernetes
- Jenkins
- Git
- Redis
- Kafka
- Swagger OpenAPI
- Lombok
- SLF4J Logging

---

# High Level Architecture

```

Web Portal
|
Mobile App
|
------------------------
API Gateway
|
------------------------
|
Authentication Service
|
--------------------------------------------------------
| | | | | | | |
User Application Workflow Document Approval Notification Audit Dashboard
Service Service Service Service Service Service Service

|
--------------------------------------------------------

|
PostgreSQL Databases

```

---

# Microservices

## 1. API Gateway

Responsibilities

- Single entry point
- Routing
- JWT Validation
- Request Logging
- Rate Limiting

---

## 2. Authentication Service

Responsibilities

- Login
- JWT Generation
- Role Based Access
- Refresh Token
- Session Management

Endpoints

POST /auth/login

POST /auth/logout

POST /auth/refresh

---

## 3. User Management Service

Responsibilities

- User Registration
- Profile Management
- Organization Management
- Role Assignment

Endpoints

POST /users

GET /users/{id}

PUT /users/{id}

DELETE /users/{id}

---

## 4. Application Service

Responsibilities

- Create Application
- Save Draft
- Submit Application
- Update Application
- Fetch Application Details

Endpoints

POST /applications

PUT /applications/{id}

GET /applications/{id}

GET /applications

---

## 5. Workflow Service

Responsibilities

- Route Applications
- Assign Tasks
- Escalation
- Approval Workflow
- Status Tracking

Workflow

Draft

↓

Submitted

↓

Under Review

↓

Clarification Required

↓

Resubmitted

↓

Approved / Rejected

---

## 6. Document Management Service

Responsibilities

- Upload Documents
- Validate Files
- Store Metadata
- Download Documents

Supported Files

PDF

JPEG

PNG

DOCX

Endpoints

POST /documents/upload

GET /documents/{id}

DELETE /documents/{id}

---

## 7. Approval Service

Responsibilities

- Approve Application
- Reject Application
- Request Clarification
- Digital Approval History

---

## 8. Notification Service

Responsibilities

- Email Notification
- SMS Notification
- Application Status Alerts
- Reminder Notifications

Communication

Kafka Events

↓

Notification Service

↓

Email/SMS

---

## 9. Audit Service

Responsibilities

- User Activity
- API Logs
- Approval History
- Change Tracking

---

## 10. Dashboard Service

Responsibilities

- Pending Applications
- Approval Statistics
- User Analytics
- Daily Reports

---

# Database Design

Users

Applications

Documents

Workflow_History

Approvals

Notifications

Audit_Logs

Roles

Permissions

Organizations

---

# Authentication Flow

Client

↓

API Gateway

↓

Authentication Service

↓

JWT Generated

↓

Gateway validates Token

↓

Forward Request

↓

Requested Microservice

---

# Application Lifecycle

User Login

↓

Create Application

↓

Save Draft

↓

Upload Documents

↓

Submit Application

↓

Workflow Engine

↓

Officer Review

↓

Clarification (Optional)

↓

Resubmission

↓

Final Approval

↓

Notification Sent

↓

Application Closed

---

# Exception Handling

GlobalExceptionHandler

ValidationException

ResourceNotFoundException

UnauthorizedException

BusinessException

DatabaseException

---

# Logging

SLF4J

Logback

Request Logs

Response Logs

Exception Logs

Audit Logs

---

# Security

Spring Security

JWT Authentication

Password Encryption

Role Based Authorization

Input Validation

CSRF Protection

SQL Injection Prevention

XSS Protection

---

# Performance Optimizations

Pagination

Database Indexing

Redis Cache

Lazy Loading

Connection Pooling

Asynchronous Processing

---

# CI/CD

Developer

↓

Git

↓

Merge Request

↓

Jenkins Pipeline

↓

Unit Tests

↓

Build

↓

Docker Image

↓

Kubernetes Deployment

↓

Production

---

# Folder Structure

src

├── controller

├── service

├── repository

├── entity

├── dto

├── mapper

├── exception

├── config

├── security

├── util

├── validator

└── resources

---

# API Documentation

Swagger UI

OpenAPI 3

JSON Response Standards

HTTP Status Codes

Validation Messages

---

# Sample Request

POST /applications

{
    "applicationName":"Factory License",
    "organization":"ABC Pvt Ltd",
    "state":"Odisha"
}

---

# Sample Response

{
    "status":"SUCCESS",
    "applicationId":"APP-2025-000123",
    "message":"Application submitted successfully."
}

---

# Skills Demonstrated

- Enterprise Backend Development
- Java 8
- Spring Boot
- REST API Development
- Hibernate & JPA
- PostgreSQL
- Microservices Architecture
- JWT Security
- Docker
- Kubernetes
- Jenkins CI/CD
- Exception Handling
- Logging
- Database Design
- Agile Development
- Git Version Control

---

# License

This repository is published solely for educational and portfolio purposes.


## About NSWS

The National Single Window System (NSWS) is a Government of India initiative that provides a unified digital platform for businesses to identify and apply for approvals, registrations, licenses, and clearances from multiple Central Ministries, Departments, and participating State Governments.

Official Website:
https://www.nsws.gov.in/

> Note: This repository is an independent portfolio project inspired by enterprise backend development experience. It does not contain any proprietary source code, confidential information, or official implementation details from NSWS or my employer.
