DevOps Internship Assignment – Multi-Service App with Nginx

This project sets up two microservices behind an Nginx reverse proxy using Docker Compose.

---

## Setup Instructions

1. **Clone the repo**:

   ```bash
   git clone https://github.com/ek-sreeraj47/Devops-Internship-Assignment.git
   cd Devops-Internship-Assignment

2. **Build & run with Docker Compose:**

   ```bash
   docker-compose up --build
   ```
3. **How Routing Works**

   Nginx listens on port 8080 and routes traffic:

4. **URL	Forwards to**

   /service1/	service1:8001

   /service2/	service2:8002

   Nginx strips the prefix (/service1, /service2) before forwarding.

5. **Bonus: Health Checks**

   Both microservices include Docker health checks to ensure they’re running:

   Service 1: /ping
   Service 2: /ping

6. **View the full docker-compose.yml:**
   
   url:  https://github.com/ek-sreeraj47/Devops-Internship-Assignment/blob/master/docker-compose.yml
