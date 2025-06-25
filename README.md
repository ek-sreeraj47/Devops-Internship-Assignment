DevOps Internship Assignment – Multi-Service App with Nginx

This project sets up two microservices behind an Nginx reverse proxy using Docker Compose.

---

## Setup Instructions

1. **Clone the repo**:

   ```bash
   git clone https://github.com/ek-sreeraj47/Devops-Internship-Assignment.git
   cd Devops-Internship-Assignment
Build & run with Docker Compose:
docker-compose up --build

-> How Routing Works
Nginx listens on port 8080 and routes traffic:

URL	Forwards to
/service1/	service1:8001
/service2/	service2:8002

Nginx strips the prefix (/service1, /service2) before forwarding.

Bonus: Health Checks
Both microservices include Docker health checks to ensure they’re running:

Service 1: /ping

Service 2: /ping

-> View the full docker-compose.yml:
url:  https://github.com/ek-sreeraj47/Devops-Internship-Assignment/blob/master/docker-compose.yml
