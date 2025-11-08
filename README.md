# Microservices-Task 
Microservices Containerization with Node.js, Docker & Docker Compose

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.
---
The system consists of four independent services that communicate over an internal Docker network:

| Service | Description | Port |

|----------|--------------|------|

| **User Service** | Manages user data | 3000 |

| **Product Service** | Handles product information | 3001 |

| **Order Service** | Processes user orders | 3002 |

| **Gateway Service** | API gateway that routes external requests to internal services | 3003 |

All services are containerized individually and orchestrated through Docker Compose.

---

## 🧩 Tech Stack

- **Node.js** -- Backend runtime
- **Express.js** -- REST API framework
- **Axios** -- HTTP client for inter-service communication
- **Docker** -- Containerization platform
- **Docker Compose** -- Multi-container orchestration

---
<img width="1312" height="165" alt="Screenshot from 2025-11-08 14-30-05" src="https://github.com/user-attachments/assets/eaf8c6bd-2e9a-4ddb-81b6-9a11209b6417" />

<img width="1312" height="566" alt="Screenshot from 2025-11-08 14-36-48" src="https://github.com/user-attachments/assets/29bda94b-a284-42f3-8b49-c1d03afb34ad" />

<img width="1312" height="655" alt="Screenshot from 2025-11-08 14-49-18" src="https://github.com/user-attachments/assets/03c83b43-ba3c-48c0-b447-ab1199e9dddd" />

<img width="735" height="541" alt="image" src="https://github.com/user-attachments/assets/2d85f9e1-b080-4506-9484-fb7d369b4fde" />





---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```

---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up
   ```
2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!
