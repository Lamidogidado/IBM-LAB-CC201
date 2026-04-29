Lab 2: Introduction to Kubernetes (Orchestration & Services)
📌 Project Overview
In this lab, I moved beyond standalone Docker containers to orchestrating applications using Kubernetes. I practiced deploying pods both imperatively and declaratively, managing scaling via Deployments, and exposing applications to traffic using Kubernetes Services.

🛠 Skills Demonstrated
Kubernetes CLI: Proficient use of kubectl to manage cluster resources.

Declarative Configuration: Defining infrastructure using YAML manifests (Deployment, Pod).

Service Discovery: Creating a ClusterIP service to load balance traffic across multiple replicas.

Pod Inspection: Troubleshooting and verifying status using describe, logs, and get pods -o wide.

🚀 The Process
1. Deploying a Single Pod
I initially deployed a single pod using an imperative command, ensuring the image could be pulled from my private IBM Cloud Container Registry using imagePullSecrets.

Bash
kubectl run hello-world --image us.icr.io/$MY_NAMESPACE/hello-world:1 --overrides='...'
2. Scaling with Deployments
To ensure high availability, I used a Deployment manifest (hello-world-apply.yaml) to maintain 3 replicas of the application.

Bash
kubectl apply -f hello-world-apply.yaml
3. Exposing the Application
I exposed the deployment as a service to create a stable entry point for traffic:

Bash
kubectl expose deployment/hello-world
4. Verifying Load Balancing
The core success of this lab was verifying that the Service correctly distributed traffic. By running a curl loop, I observed the cluster responding from different pod hostnames:

Bash
# Verification Loop
for i in `seq 10`; do curl -L localhost:8001/.../proxy; done

# Observed Load Balancing:
Hello world from hello-world-5865d57dfd-z9ccn!
Hello world from hello-world-5865d57dfd-cft5x!
Hello world from hello-world-5865d57dfd-nkrgc!