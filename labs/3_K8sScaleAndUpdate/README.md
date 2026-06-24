# Lab 3: Scaling and Rolling Updates in Kubernetes

## 📌 Project Overview
In this final lab, I simulated real-world application maintenance workflows on a Kubernetes cluster. I practiced horizontal autoscaling to handle simulated holiday traffic surges and performed an active application migration to a newer code version using an automated **Rolling Update** strategy.

## 🛠 Skills Demonstrated
* **Horizontal Scaling:** Utilizing `kubectl scale` to seamlessly dynamically alter pod replica quantities.
* **Rolling Updates:** Triggering zero-downtime updates via image configuration changes using `kubectl set image`.
* **Resilient Infrastructure Analysis:** Monitoring production cluster stability and observing live request routing traffic during backend instance terminations.

## 🚀 The Process

### 1. Scaling Resources
To ensure the infrastructure could support high volume constraints, I horizontally scaled the application deployment setup to **10 concurrent replicas**:
```bash
kubectl scale deployment/hello-world --replicas=10