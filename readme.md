# CloudNative - Restaurant Ordering System
This is a comprehensive restaurant ordering system built using Spring Cloud. It provides functionalities for both ordinary users and administrators to manage orders, users, menus, and more. A CloudNative program (k8s+containered) is based on this order-system to build.

## Microservices
The system is composed of several microservices:


Eureka Server: Service registry for microservices.

Config Server: Centralized configuration management.

Gateway Server: Gateway acts as a single entry point to the micro-service, handling request routing, authentication, and load balancing.

Account Service: Manages user accounts and authentication.

Menu Service: Handles menu management operations.

Order Service: Manages order information.

User Service: Manages user information.


## Functionality
### For Ordinary Users:
Register an account.

Place orders.

View order status.

### For Administrators:
Add, delete, or edit users.

Manage order statuses (e.g., mark orders as completed).

Add, edit, or delete menu items.

## Getting Started
### Clone the Repository:
git clone (https://github.com/SaintNameless/CloudNative)
### Set up Configuration:
Update configuration files in the Config Server and the Gateway Server according to your environment.
### Build and Package Microservices:
Build and package each microservice using Maven.
'''Bash
mvn clean package
'''
Using Dockerfile to build images.
'''Bash
docker build -f .
'''
Deploy your images on the k8s-environment.
'''Bash
kubectl create -f k8s-deployment/*.yaml
'''
Ensure proper communication between microservices.

### Database Setup:
Create a MySQL database and import the provided schema.


## Contributors
Gui Qing, Wang Lijin, Yang Shuhang

## Acknowledge
Yanxu(Tina) (https://github.com/SaintNameless/CloudNative)
