Web Application Deployment with CI/CD, Docker, Nginx, Prometheus & Grafana on AWS EC2

This project demonstrates a complete DevOps pipeline for deploying a React + Node.js full-stack application using modern DevOps tools and cloud infrastructure.

The system includes:

Frontend: React

Backend: Node.js / Express

Containerization: Docker

Reverse Proxy: Nginx

CI/CD Pipeline: GitHub Actions

Monitoring: Prometheus + Grafana

Infrastructure: AWS EC2

The application is automatically deployed whenever code is pushed to the main branch.

Architecture
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
   └── Grafana (Visualization Dashboard)
Technologies Used
Technology	Purpose
React	Frontend UI
Node.js / Express	Backend API
Docker	Containerization
Docker Compose	Multi-container orchestration
Nginx	Reverse proxy
GitHub Actions	CI/CD automation
AWS EC2	Cloud hosting
Prometheus	Metrics collection
Grafana	Monitoring dashboards
Project Structure
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
└── .github
    └── workflows
        └── deploy.yml      # GitHub Actions CI/CD pipeline
Docker Containers

The application runs using the following containers:

Container	Description
frontend	React frontend
backend	Node.js API
nginx	Reverse proxy server
prometheus	Monitoring metrics
grafana	Visualization dashboards
CI/CD Pipeline (GitHub Actions)

The pipeline automatically performs the following steps when code is pushed:

Checkout the repository

Build Docker images for frontend and backend

Push images to Docker Hub

Connect to AWS EC2 via SSH

Pull latest Docker images

Restart containers using Docker Compose

Example workflow snippet:

docker compose pull
docker compose up -d --remove-orphans
AWS Deployment

The application is hosted on an AWS EC2 Ubuntu instance.

Ports used:

Port	Service
80	Application via Nginx
3000	Grafana dashboard
9090	Prometheus
22	SSH
Monitoring Setup
Prometheus

Prometheus collects metrics from:

Node Exporter (system metrics)

Application services

Grafana

Grafana visualizes metrics using dashboards.

Example metrics:

CPU usage

Memory usage

Disk utilization

Network traffic

Grafana Dashboard

Default Grafana login:

Username: admin
Password: admin

Import dashboard:

Node Exporter Dashboard ID: 1860
How to Run Locally

Clone the repository:

git clone https://github.com/harshit075/DevOps_kadel_task.git

Navigate to project:

cd project

Start containers:

docker compose up -d

