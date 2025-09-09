# 🚀 Node.js + Redis Counter App

A simple Node.js application that counts homepage visits using Redis.  
This guide explains the project, setup steps, and how to run it in two ways:

1. **Standalone mode**: Run Redis and the Node.js app in separate containers.  
2. **Docker Compose mode (recommended)**: Run everything with a single command.

---

## 📂 Project Overview

- A Node.js app with two endpoints:  
  - `/` to view and increment the visit counter  
  - `/health` to check if the service is running  
- Redis is used as an in-memory store to track visit counts.  
- Both Node.js and Redis are containerized using Docker.  
- Environment variables allow easy customization of ports and hostnames.

---

## 🗂️ Files Included

- **app.js**: Main server file with Express routes and Redis integration.  
- **package.json**: Node.js dependencies and scripts.  
- **.env**: Configurable environment variables like app port and Redis host.  
- **Dockerfile**: Instructions to build the Node.js application image.  
- **docker-compose.yml**: Runs both the Node.js app and Redis with one command.  
- **README.md**: This documentation.

---

## 🔧 Prerequisites

- Docker installed on your system.  
- Docker Compose installed.  
- Optional: Remove or stop any local Redis installation to avoid port conflicts.

---

## 🌟 Scenario 1: Standalone Mode (Manual)

If you want to manually run the containers separately:

1. Build the Node.js app image.  
2. Start Redis in its own container.  
3. Run the Node.js container and link it to Redis.  
4. Access the application at **http://localhost:8000**.  
5. Stop and remove containers manually when done.  

This is useful for learning Docker basics or doing custom setups.

---

## 🌟 Scenario 2: Docker Compose Mode (Recommended)

This approach automates everything and is easier for development and production:

1. Run `docker compose up` to start the app and Redis together.  
2. Access the app at **http://localhost:8000**.  
3. Use `docker compose down` to stop everything.  

**Benefits of this approach:**  
- Automatic service discovery between containers (no manual linking).  
- One command to build, start, and stop services.  
- Easier to scale and maintain.

---

## 🔍 Debugging and Development Tips

- View logs for any service with `docker logs`.  
- Rebuild containers after code changes using `docker compose up --build`.  
- Open a shell inside a container using `docker exec`.  
- Adjust `.env` variables to change ports or service hostnames.  
- Remove Redis host port exposure in Docker Compose if you want Redis to be internal-only.

---

## 💡 Best Practices

- Always use Docker Compose for simplicity.  
- Reference Redis by its service name `redis` inside containers, not `localhost`.  
- Remove or stop local Redis installations to avoid conflicts on port 6379.  
- Use environment variables to keep configuration flexible.

---

This setup allows you to run a Node.js + Redis application entirely in Docker.  
For simplicity, reliability, and easier scaling, **Docker Compose is the recommended approach**.
