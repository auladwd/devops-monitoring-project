# 🚀 DevOps Monitoring and Deployment Project

## 📌 Project Overview

This project demonstrates a complete DevOps monitoring and deployment solution using Infrastructure as Code (Terraform), CI/CD pipeline (GitHub Actions), and a modern observability stack (Grafana, Loki, Promtail, and Node Exporter).

The system provisions a cloud server, deploys monitoring tools, and visualizes system metrics and logs in real-time.

---

## 🛠️ Technologies Used

* **Terraform** – Infrastructure provisioning
* **AWS EC2** – Cloud server
* **Docker & Docker Compose** – Containerized deployment
* **Prometheus** – Metrics collection
* **Node Exporter** – System metrics
* **Grafana** – Data visualization
* **Loki** – Log aggregation
* **Promtail** – Log shipping agent
* **GitHub Actions** – CI/CD automation

---

## ☁️ Infrastructure Provisioning (Terraform)

Terraform is used to provision an AWS EC2 instance.

### Steps:

```bash
cd terraform
terraform init
terraform plan
terraform apply
```

### Output:

* EC2 instance created successfully
* Public IP generated

---

## ⚙️ Monitoring Stack Setup

Monitoring tools are deployed using Docker Compose.

### Services:

* Prometheus → Collects metrics
* Node Exporter → Provides system metrics (CPU, Memory, Disk, Network)
* Grafana → Dashboard visualization
* Loki → Collects logs
* Promtail → Sends logs to Loki

### Run the stack:

```bash
cd monitoring
docker-compose up -d
```

---

## 📊 Grafana Dashboard

Grafana is used to visualize system performance and logs.

### Access:

```
http://54.159.0.158:3000
```

### Default Login:

* Username: admin
* Password: admin

### Dashboard Features:

* CPU Usage
* Memory Usage
* Disk Usage
* Network Traffic
* System Logs (via Loki)

### Dashboard Import:

* Node Exporter Dashboard ID: **1860**

---

## 🔄 CI/CD Pipeline (GitHub Actions)

CI/CD pipeline is implemented using GitHub Actions.

### Workflow:

* Trigger: Push to `main` branch
* Steps:

  * Checkout repository
  * Connect to EC2 via SSH
  * Deploy updated Docker containers

### Workflow File:

```
.github/workflows/deploy.yml
```

---

## 📁 Project Structure

```
devops-monitoring-project/
│
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
│
├── monitoring/
│   ├── docker-compose.yml
│   ├── prometheus.yml
│   └── loki-config.yml
│
├── dashboards/
│   └── grafana-dashboard.json
│
├── .github/workflows/
│   └── deploy.yml
│
└── README.md
```

## 🔐 Security Notes

* Sensitive files like `.tfstate`, `.pem`, and `.env` are excluded using `.gitignore`
* GitHub Secrets are used for storing:

  * EC2 Host IP
  * SSH Private Key

---

## ✅ Conclusion

This project successfully demonstrates:

* Infrastructure provisioning using Terraform
* Automated deployment using CI/CD
* Real-time monitoring using Grafana stack
* Centralized logging using Loki

It reflects a complete DevOps workflow from infrastructure setup to monitoring and automation.

---

## 📌 Submission

GitHub Repository Link:

```
(https://github.com/auladwd/devops-monitoring-project)
```

---
