#  Web App Deployment with CI/CD, Docker, Nginx, Prometheus & Grafana on AWS

This project demonstrates a **complete DevOps pipeline** for deploying a **React + Node.js application** using modern DevOps tools and AWS cloud infrastructure.

Whenever code is pushed to the **main branch**, GitHub Actions automatically builds Docker images, pushes them to Docker Hub, and redeploys the application on an AWS EC2 server.

---

# Architecture

```
Developer
   │
   │ Push Code
   ▼
GitHub Repository
   │
   │ CI/CD Pipeline
   ▼
GitHub Actions
   │
   │ Build Docker Images
   │ Push Images to Docker Hub
   ▼
Docker Hub
   │
   │ Pull Images
   ▼
AWS EC2 Instance
   │
   ├── Nginx (Reverse Proxy)
   ├── React Frontend Container
   ├── Node Backend Container
   ├── Prometheus (Metrics Collection)
   └── Grafana (Monitoring Dashboard)
```

---

# Technologies Used

- **React** – Frontend UI  
- **Node.js / Express** – Backend API  
- **Docker** – Containerization  
- **Docker Compose** – Multi-container management  
- **Nginx** – Reverse proxy server  
- **GitHub Actions** – CI/CD automation  
- **AWS EC2** – Cloud hosting  
- **Prometheus** – Metrics collection  
- **Grafana** – Monitoring dashboards  

---

# Project Structure

```
project-root
│
├── client/                 # React frontend
│   └── Dockerfile
│
├── server/                 # Node backend
│   └── Dockerfile
│
├── docker-compose.yml      # Multi-container configuration
├── nginx.conf              # Nginx reverse proxy configuration
├── prometheus.yml          # Prometheus configuration
│
└── .github/
    └── workflows/
        └── deploy.yml      # GitHub Actions CI/CD pipeline
```

---

# Docker Containers

The application runs using the following containers:

| Container | Description |
|-----------|-------------|
| frontend | React frontend |
| backend | Node.js API |
| nginx | Reverse proxy server |
| prometheus | Metrics collection |
| grafana | Monitoring dashboard |

---

# CI/CD Pipeline (GitHub Actions)

The CI/CD pipeline performs these steps automatically:

1. Checkout the repository
2. Build Docker images for frontend and backend
3. Push Docker images to Docker Hub
4. Connect to AWS EC2 via SSH
5. Pull the latest images
6. Restart containers using Docker Compose

Example deployment command:

```bash
docker compose pull
docker compose up -d --remove-orphans
```

---

# AWS Deployment

The application runs on an **AWS EC2 Ubuntu instance**.

Required ports:

| Port | Service |
|-----|--------|
| 80 | Web Application |
| 3000 | Grafana Dashboard |
| 9090 | Prometheus |
| 22 | SSH |

---

# Monitoring Setup

### Prometheus
Prometheus collects metrics from:

- Node Exporter (system metrics)
- Application containers

### Grafana
Grafana visualizes the metrics using dashboards.

Metrics monitored:

- CPU usage
- Memory usage
- Disk utilization
- Network traffic

---

# Grafana Dashboard

Default login credentials:

```
Username: admin
Password: admin
```

Import dashboard:

```
Node Exporter Dashboard ID: 1860
```

---

# Run Locally

Clone the repository:

```bash
git clone https://github.com/harshit075/DevOps_kadel_task.git
```

Navigate to project folder:

```bash
cd project
```

Start containers:

```bash
docker compose up -d
```

Open the application:

```
http://localhost
```

---


