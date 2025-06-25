# 🚀 Multi-Service App with Nginx Reverse Proxy

This project includes two lightweight microservices and an Nginx reverse proxy, all containerized using Docker Compose.

---

## ✅ Setup Instructions

1. **Clone the project** and navigate into the folder:

   ```bash
   git clone <your-repo-url>
   cd project-root
   ```

2. **Build and run the containers**:

   ```bash
   docker-compose up --build
   ```

3. **Access the app** in your browser or via `curl`:
   - http://localhost:8080/service1/ping
   - http://localhost:8080/service2/hello

---

## 🌐 How Routing Works

Nginx listens on port **8080** and routes traffic based on the URL path:

| Path Prefix        | Proxied To          |
|--------------------|---------------------|
| `/service1/`       | `service1:8001`     |
| `/service2/`       | `service2:8002`     |

Nginx removes the `/service1` or `/service2` prefix before forwarding to the target service.

---

## ⭐ Bonus: Health Checks

Both services have Docker health checks configured to ensure reliability:

- **Service 1**: `http://localhost:8001/ping`
- **Service 2**: `http://localhost:8002/ping`

Docker automatically checks the service health at regular intervals.

---

Feel free to extend this with logging, CI/CD, or cloud deployment.
