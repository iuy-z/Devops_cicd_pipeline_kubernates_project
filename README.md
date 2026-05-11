# 🚀 DevOps CI/CD Pipeline with Docker, Jenkins, Kubernetes & Grafana

A complete DevOps project demonstrating an automated **CI/CD (Continuous Integration and Continuous Deployment)** pipeline for a Flask web application using **Docker, Jenkins, Kubernetes (Minikube), and Grafana**.

This project showcases how modern DevOps tools can be integrated to automate application building, deployment, and monitoring in a cloud environment.

---

## 📌 Project Overview

This project implements a full DevOps workflow that automates:

- Source code management using GitHub
- Containerization using Docker
- CI/CD automation using Jenkins
- Application deployment using Kubernetes
- Monitoring and visualization using Grafana & Prometheus

The pipeline automatically fetches the latest code, builds a Docker image, pushes it to Docker Hub, deploys the application to Kubernetes, and sets up monitoring dashboards.

---

## 🛠 Technologies Used

| Tool | Purpose |
|------|---------|
| **Flask** | Web application framework |
| **Docker** | Containerization |
| **Jenkins** | CI/CD automation |
| **Kubernetes (Minikube)** | Container orchestration |
| **Grafana** | Monitoring dashboard |
| **Prometheus** | Metrics collection |
| **GitHub** | Version control |
| **AWS EC2** | Cloud deployment environment |

---

## 📂 Project Structure

```bash
devops-cicd-pipeline/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── Jenkinsfile
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── monitoring/
│   └── monitoring-all.yaml
│
└── README.md
```

---

## ⚙ Features

✅ Automated CI/CD pipeline  
✅ Dockerized Flask application  
✅ Kubernetes deployment with multiple replicas  
✅ Docker image push to Docker Hub  
✅ Monitoring with Grafana & Prometheus  
✅ Cloud deployment on AWS EC2  

---

## 🔄 CI/CD Pipeline Workflow

```text
GitHub → Jenkins → Docker Build → Docker Hub → Kubernetes Deployment → Grafana Monitoring
```

---

## 🐳 Docker Setup

### Build Docker Image

```bash
docker build -t flask-user-app .
```

### Run Docker Container

```bash
docker run -p 5000:5000 flask-user-app
```

---

## 🔧 Jenkins Setup

Install Jenkins and configure:

- GitHub credentials
- Docker Hub credentials
- Kubernetes access permissions

### Jenkins Pipeline Stages

1. **Code Fetch** – Clone repository from GitHub  
2. **Docker Build & Push** – Build and push image to Docker Hub  
3. **Kubernetes Deployment** – Deploy app using YAML files  
4. **Monitoring Setup** – Deploy Grafana and Prometheus  

---

## ☸ Kubernetes Deployment

### Apply Deployment

```bash
kubectl apply -f k8s/deployment.yaml
```

### Apply Service

```bash
kubectl apply -f k8s/service.yaml
```

### Verify Pods

```bash
kubectl get pods
```

### Verify Services

```bash
kubectl get svc
```

---

## 🌐 Access the Application

Port-forward the service:

```bash
kubectl port-forward --address 0.0.0.0 svc/flask-service 5000:5000
```

Open in browser:

```text
http://localhost:5000
```

---

## 📊 Grafana Monitoring

Access Grafana dashboard:

```bash
kubectl port-forward -n monitoring svc/grafana 3000:3000 --address 0.0.0.0
```

Open in browser:

```text
http://localhost:3000
```

---

## ⚠ Issue Faced & Solution

### Jenkins Could Not Access Kubernetes

**Problem:**  
Jenkins failed to connect to the Kubernetes cluster due to incorrect kubeconfig permissions.

**Solution:**  
Update Kubernetes config path:

```bash
/var/lib/jenkins/.kube/config
```

Restart Minikube:

```bash
minikube stop
minikube start
```

After this, Jenkins successfully deployed the application.

---

## 🚀 Clone This Repository

```bash
git clone https://github.com/iuy-z/Devops_cicd_pipeline_kubernates_project.git
cd Devops_cicd_pipeline_kubernates_project
```

---

## 📚 Learning Outcomes

- Understanding CI/CD pipelines
- Docker containerization
- Jenkins automation
- Kubernetes deployment
- Monitoring with Grafana
- Cloud deployment on AWS EC2

---

## 👩‍💻 Author

**Irum Imtiaz**  


---

## 📄 License

This project is created for educational and academic purposes.

---

## ⭐ Repository Link

https://github.com/iuy-z/devops-cicd-pipeline
