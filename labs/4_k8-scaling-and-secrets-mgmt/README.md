# Lab 4: Automated Scaling (HPA) and Secrets Management

## 📌 Project Overview
This lab focused on security hardening and automated performance elastic scaling. I decoupled sensitive application credentials from code architectures using native Kubernetes Secrets and configured a Horizontal Pod Autoscaler (HPA) to scale dynamically based on active resource consumption metrics.

## 🛠️ Skills Demonstrated
* **Secrets Deconstruction & Injection:** Externalized authentication profiles away from the core container image filesystem using secure environment variables.
* **Horizontal Pod Autoscaling (HPA):** Created reactive automated threshold parameters monitoring memory and CPU demands.
* **Runtime Container Inspection:** Validated successful deployment states via remote active container configuration query strings.

## 🚀 The Process

### 1. Generating Secure Variables
Credentials were built within an independent `secret.yaml` manifest and loaded directly into the namespace cluster context:
```bash
kubectl apply -f secret.yaml