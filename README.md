# Django Notes App – Dockerized Deployment

A containerized **Django Notes Application** deployed using **Docker, Docker Compose, MySQL, Gunicorn, and Nginx**.

This project demonstrates how to run a production-ready Django application using containerized services and service orchestration with Docker Compose.

---

# Project Architecture

The application uses a multi-container architecture:

```
User Browser
     │
     ▼
   Nginx
     │
     ▼
  Gunicorn
     │
     ▼
   Django
     │
     ▼
   MySQL
```

### Services

| Service            | Purpose                                   |
| ------------------ | ----------------------------------------- |
| **Nginx**          | Reverse proxy to handle incoming requests |
| **Gunicorn**       | Production WSGI server for Django         |
| **Django App**     | Main application logic                    |
| **MySQL**          | Database for storing notes                |
| **Docker Compose** | Orchestrates all containers               |

---

# Project Structure

```
django-notes-app
│
├── backend/
│   ├── notesapp/
│   ├── api/
│   ├── manage.py
│
├── nginx/
│   └── default.conf
│
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── .env
└── README.md
```

---

# Features

* Dockerized Django application
* MySQL database container
* Gunicorn for production WSGI server
* Nginx reverse proxy
* Health checks for services
* Docker networking between services
* Persistent MySQL data using Docker volumes

---

# Prerequisites

Make sure the following tools are installed:

* Docker
* Docker Compose
* Git

Check versions:

```
docker --version
docker compose version
```

---

# Clone the Repository

```
git clone https://github.com/Pardeepkaur32/django-notes-app.git
cd django-notes-app
```

---

# Environment Variables

Create a `.env` file in the project root.

Example:

```
DEBUG=1
SECRET_KEY=your_secret_key
DB_NAME=notes_db
DB_USER=root
DB_PASSWORD=root
DB_HOST=db
DB_PORT=3306
```

---

# Build and Run the Project

Start the containers:

```
docker compose up --build
```

Run in detached mode:

```
docker compose up -d --build
```

---

# Access the Application

Open your browser:

```
http://localhost
```

Django Admin Panel:

```
http://localhost/admin
```

---

# Docker Containers

Check running containers:

```
docker ps
```

Expected containers:

```
nginx
django_app
mysql_db
```

---

# Database Persistence

MySQL data is stored using Docker volumes:

```
docker volume ls
```

This ensures database data remains even if containers stop.

---

# Useful Docker Commands

Stop containers:

```
docker compose down
```

Stop and remove volumes:

```
docker compose down -v
```

View container logs:

```
docker compose logs
```

Restart containers:

```
docker compose restart
```

---

# Health Checks

Health checks are implemented for:

* MySQL database
* Django application
* Nginx service

This ensures services start only when dependencies are healthy.

---

# Technologies Used

* Python
* Django
* MySQL
* Gunicorn
* Nginx
* Docker
* Docker Compose

---

# Learning Objectives

This project demonstrates:

* Containerizing Django applications
* Multi-container architecture
* Reverse proxy setup with Nginx
* Database containerization
* Docker networking
* Health checks in Docker Compose
* Production-style deployment architecture

---

# Future Improvements

Possible enhancements:

* Add Redis caching
* Implement CI/CD pipeline (GitHub Actions / Jenkins)
* Deploy on Kubernetes
* Add HTTPS with Let's Encrypt
* Add monitoring with Prometheus & Grafana

---

# Author

**Pardeep Kaur**

DevOps & Cloud Enthusiast
Focused on Docker, Kubernetes, CI/CD, and Cloud Infrastructure.

---

# License

This project is open-source and available for learning purposes.
