# Kubernetes Deployment Portfolio

![Kubernetes CI](https://github.com/HagarMeselhi/kubernetes-deployment-portfolio/actions/workflows/kubernetes-ci.yml/badge.svg)

A Kubernetes deployment project created as part of my DevOps / Cloud / Platform Engineering portfolio.

## What this project demonstrates

- Kubernetes Deployment
- Kubernetes Service
- Kubernetes Ingress
- ConfigMap and Secret usage
- Resource requests and limits
- Readiness and liveness probes
- Horizontal Pod Autoscaler
- Kustomize structure
- GitHub Actions CI for Kubernetes manifest validation

## Application Image

This project deploys the Docker image from my DevOps Portfolio API project:

ghcr.io/hagarmeselhi/devops-portfolio-api:latest

## Kubernetes Resources

The project defines:

- Namespace
- ConfigMap
- Secret
- Deployment
- Service
- Ingress
- HorizontalPodAutoscaler

## Architecture

External traffic reaches the application through an Ingress.

Ingress forwards traffic to the Service.

The Service forwards traffic to application Pods managed by the Deployment.

The Deployment runs 2 replicas of the API container.

The application exposes a health check endpoint:

/health

## Important Note

This repository is designed for portfolio and validation purposes.

The CI pipeline validates Kubernetes YAML manifests.

It does not deploy to a live Kubernetes cluster automatically.

## Apply manually

If a Kubernetes cluster is available, the manifests can be applied using:

kubectl apply -k k8s/

## Delete manually

kubectl delete -k k8s/

## CI/CD

GitHub Actions runs automatically on every push and pull request.

The workflow validates Kubernetes manifests using kubeconform.

## Author

Hagar Meselhi
