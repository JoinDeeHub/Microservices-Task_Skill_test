<<<<<<< HEAD
# Microservices-Task 
Microservices Containerization with Node.js, Docker & Docker Compose
=======

# Microservices-Task
>>>>>>> b64b1f6 (Remove microservices and add Docker configuration for user, product, order, and gateway services)

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

# 🚀 Microservices Containerization with Node.js, Docker & Docker Compose

### 📘 Project Overview

This project demonstrates containerization and orchestration of a **microservices-based Node.js application** using **Docker** and **Docker Compose**.  

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

## 🏗️ Project Structure

submission/

├── user-service/

│ ├── app.js

│ ├── package.json

│ └── Dockerfile

├── product-service/

│ ├── app.js

│ ├── package.json

│ └── Dockerfile

├── order-service/

│ ├── app.js

│ ├── package.json

│ └── Dockerfile

├── gateway-service/

│ ├── app.js

│ ├── package.json

│ └── Dockerfile

├── docker-compose.yml

└── README.md

yaml

---

## 🧭 Project Architecture

Below diagram illustrates the communication flow and orchestration between all microservices using Docker Compose.

<img width="2595" height="937" alt="image" src="https://github.com/user-attachments/assets/486c8a6b-52cd-415a-be3c-9af3303ea4f8" />

---

## ⚙️ Prerequisites

Before starting, ensure the following are installed:

- **Docker Engine** ≥ 20.x  
- **Docker Compose** ≥ 1.27 (or integrated Docker Compose v2)  
- **Git** for cloning the repository

Verify installation:

docker --version

docker-compose --version

🧱 Setup & Installation

Clone the repository

git clone https://github.com/`<your-username>`/Microservices-Task.git

cd Microservices-Task

Build and start all services

docker-compose up --build -d

Verify running containers

docker-compose ps

Expected:

Name                Command               State   Ports

---

user-service        node app.js           Up      0.0.0.0:3000->3000/tcp

product-service     node app.js           Up      0.0.0.0:3001->3001/tcp

order-service       node app.js           Up      0.0.0.0:3002->3002/tcp

gateway-service     node app.js           Up      0.0.0.0:3003->3003/tcp

Check logs

docker-compose logs -f

🔍 Testing the Services

✅ Health Check Endpoints

Service  Endpoint  Example Response

User  http://localhost:3000/health  { "status": "User Service is healthy" }

Product  http://localhost:3001/health  { "status": "Product Service is healthy" }

Order  http://localhost:3002/health  { "status": "Order Service is healthy" }

Gateway  http://localhost:3003/health  { "status": "Gateway Service is healthy" }

🌐 API Testing via Gateway

Fetch Users

curl http://localhost:3003/api/users

Fetch Products

curl http://localhost:3003/api/products

Create an Order

curl -X POST http://localhost:3003/api/orders

  -H "Content-Type: application/json"

  -d '{"userId":1,"productId":2}'

Get All Orders

curl http://localhost:3003/api/orders

If all endpoints respond successfully, the system is fully operational.

🧰 Common Commands

Action  Command

Build & Run containers  docker-compose up --build -d

Stop containers  docker-compose down

View logs  docker-compose logs -f

Rebuild specific service  docker-compose build user-service

Access a container shell  docker exec -it user-service sh

Remove all containers & images  docker-compose down --rmi all --volumes

🧠 Troubleshooting

Issue  Possible Cause  Fix

Port 3000 already in use  Grafana or another service using port  Stop Grafana (sudo systemctl stop grafana-server) or change Grafana's port

🧾 Sample Output

$ docker-compose up --build -d

Building user-service

Successfully built `<hash>`

Successfully tagged user-service:latest

...

Creating network "microservices-task_ms-net" with driver "bridge"

Creating user-service ... done

Creating product-service ... done

Creating order-service ... done

Creating gateway-service ... done

$ curl http://localhost:3003/health

{"status":"Gateway Service is healthy"}

📸 Screenshots (Attach in Submission)

Include the following screenshots in the screenshots/ folder:

Output of docker-compose ps

Gateway health check in browser

Successful order creation via cURL or Postman

Logs showing all services running

📦 Submission Instructions

Ensure final directory matches:

submission/

├── user-service/Dockerfile

├── product-service/Dockerfile

├── order-service/Dockerfile

├── gateway-service/Dockerfile

├── docker-compose.yml

├── README.md

└── screenshots/

Compress into ZIP:

zip -r submission.zip submission/

Upload ZIP to VLearn portal and share your GitHub fork URL.

👩‍💻 Author

DEEPIKA NARENDRAN [DevOps B13]

Skill Test 1 -- Cloud & Containers

Microservices Containerization Assignment
