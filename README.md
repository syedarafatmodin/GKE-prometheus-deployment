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

## Project Structure

The repository is organized into application source code and Kubernetes manifests:

```text
gke-prometheus-deployment/
├── app/
│   ├── Dockerfile          # Multi-stage build for Go application
│   ├── main.go             # Source code for the hello-web server
│   └── go.mod              # Go module definition
├── k8s/
│   ├── deployment.yaml     # Main GKE deployment configuration
│   ├── service.yaml        # LoadBalancer service definition
│   ├── pod-monitoring.yaml # Custom resource for Prometheus scraping
│   └── prometheus-app.yaml # Sidecar/Exporter configuration
└── README.md               # Project documentation
