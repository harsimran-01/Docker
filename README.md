# 🐳 Docker Setup (MongoDB + Mongo Express + Node App)

This project demonstrates a complete **Docker-based development environment** using:

* MongoDB (Database)
* Mongo Express (Database UI)
* Node.js (Backend Application)

---

## 📸 Docker Volumes (Data Persistence)

![Docker Volumes](./assets/docker-volumes.png)

> This shows Docker volumes used to persist MongoDB data even after container restarts.

---

## 📌 Features

* Containerized MongoDB database
* Web-based MongoDB UI (Mongo Express)
* Docker networking between services
* Environment variable configuration
* Data persistence using volumes
* Multi-container setup using Docker Compose

---

## 🛠️ Tech Stack

* Docker
* Docker Compose
* Node.js
* MongoDB
* Mongo Express

---

## 📁 Project Structure

```
test-app/
│── Dockerfile
│── mongodb.yaml
│── server.js
│── package.json
│── .dockerignore
│── node_modules/
│── assets/
    └── docker-volumes.png
```

---

## ⚙️ Prerequisites

* Docker Desktop
* Git
* Node.js (optional for local dev)

---

## 🚀 Getting Started

### 1. Clone Repository

```
git clone <your-repo-url>
cd test-app
```

---

### 2. Start Services

```
docker compose -f mongodb.yaml up -d
```

---

### 3. Verify Containers

```
docker ps
```

---

### 4. Access Mongo Express

```
http://localhost:8081
```

### 🔐 Login Credentials

```
Username: admin
Password: qwerty
```

---

## 🐳 Running Node App

### Build Image

```
docker build -t test-app .
```

### Run Container

```
docker run -p 3000:3000 test-app
```

---

## 🌐 Networking

Containers communicate using service names:

```
mongodb://admin:qwerty@mongo:27017
```

---

## 💾 Data Persistence

```
E:/Docker/data:/data/db
```

* Prevents data loss
* Stores MongoDB data locally

---

## 📄 Environment Variables

### MongoDB

```
MONGO_INITDB_ROOT_USERNAME=admin
MONGO_INITDB_ROOT_PASSWORD=qwerty
```

### Mongo Express

```
ME_CONFIG_MONGODB_ADMINUSERNAME=admin
ME_CONFIG_MONGODB_ADMINPASSWORD=qwerty
ME_CONFIG_MONGODB_URL=mongodb://admin:qwerty@mongo:27017
ME_CONFIG_BASICAUTH_USERNAME=admin
ME_CONFIG_BASICAUTH_PASSWORD=qwerty
```

---

## 🔍 Useful Commands

```
docker ps
docker ps -a
docker logs mongo-express
docker start <container>
docker stop <container>
```

---

## ⚠️ Common Issues

* Docker not running → Start Docker Desktop
* YAML errors → Fix indentation & syntax
* Login issues → Check environment variables

---

## 📌 Best Practices

* Use `.dockerignore`
* Avoid copying `node_modules`
* Use volumes for DB
* Use Docker Compose

---

## 🚀 Future Improvements

* Add Node app to docker-compose
* Use `.env` file
* Deploy with Docker
* Add CI/CD

---

## 👩‍💻 Author

Harsimran Kaur

---
