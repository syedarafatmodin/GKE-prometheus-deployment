# GKE Deployment & Monitoring Demo

## Overview
This project demonstrates a cloud-native deployment pipeline on Google Kubernetes Engine (GKE). It features a containerized Go application with integrated monitoring, autoscaling, and error alerting.

## Tech Stack
* **Cloud:** Google Cloud Platform (GCP)
* **Orchestrator:** Google Kubernetes Engine (GKE) (Standard Cluster)
* **Containerization:** Docker & Artifact Registry
* **Monitoring:** Managed Service for Prometheus
* **IaC/Config:** Kubernetes Manifests (YAML)

## Key Features Implemented
* **Cluster Configuration:** Deployed a regional GKE cluster with Node Autoscaling enabled.
* **Observability:** Integrated Managed Prometheus for scraping custom pod metrics.
* **Alerting:** Configured Cloud Monitoring alerts for specific log-based errors (`InvalidImageName`).
* **Deployment Strategy:** Performed rolling updates to transition from v1 to v2 of the application without downtime.
* **Load Balancing:** Exposed the application via an External Load Balancer.

## Project Structure
* `manifests/`: Kubernetes deployment and service configurations.
* `main.go`: Sample Go application serving HTTP requests.
* `Dockerfile`: Multi-stage build for containerizing the Go app.
* `pod-monitoring.yaml`: Custom resource definition for Prometheus scraping.

gke-prometheus-deployment/
├── app/
│   ├── Dockerfile
│   ├── main.go
│   └── go.mod (if you have one)
├── k8s/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── pod-monitoring.yaml
│   └── prometheus-app.yaml
└── README.md
