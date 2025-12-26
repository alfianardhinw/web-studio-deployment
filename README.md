# Wibe Studio Frontend Deployment

## Project Overview
This project demonstrates how to deploy a frontend React application to AWS EC2 using Docker and GitHub Actions CI/CD.  
Monitoring is handled by an external Prometheus server running on a separate machine (WSL) to simulate a real-world distributed monitoring setup.

---

## Architecture
- Local (WSL): Development environment & Prometheus monitoring
- AWS EC2: Frontend application (Dockerized) + Node Exporter
- GitHub Actions: CI/CD pipeline
- AWS Auto Scaling Group: Automatic instance scaling

---

## Tech Stack
- React (Frontend)
- Docker & Docker Compose
- AWS EC2 & Auto Scaling
- GitHub Actions (CI/CD)
- Prometheus
- Node Exporter

---

## Deployment Flow
1. Developer pushes code to GitHub
2. GitHub Actions triggers CI/CD pipeline
3. Application is deployed to EC2 via SSH
4. Frontend runs inside Docker container
5. Node Exporter exposes system metrics
6. Prometheus (external) scrapes metrics from EC2

---

## Monitoring
Prometheus is intentionally deployed outside EC2 to simulate a centralized monitoring server.

Metrics exposed:
- Memory usage

---

## Auto Scaling
EC2 instances are managed by an Auto Scaling Group.
Scaling policy:
- Scale out when CPU usage > 70%
- Scale in when CPU usage < 30%

---

## Author
Ardhi

