# IBM Cloud Cloud-Native Engineering Labs (CC201)

Welcome to my Cloud-Native Engineering showcase. This repository chronicles my practical journey through containerization, cluster orchestration, and high-availability deployment strategies utilizing **Docker**, **Kubernetes (K8s)**, and **IBM Cloud Container Registry**.

## 🏗️ Core Architecture Journey

The series progresses sequentially from packaging a single application component to architecting a fully resilient, load-balanced, and auto-scaled microservice ecosystem.

```text
[ Local Application ] ──(Lab 1: Docker)──> [ Container Image ]
                                                    │
                                         (Lab 2: Kubernetes Service)
                                                    │
                                                    ▼
[ User Requests ] ──> [ ClusterIP Load Balancer ] ──┬──> [ Pod Replica 1 ]
                                                    ├──> [ Pod Replica 2 ]
                                                    └──> [ Pod Replica 3 ]
                                                    │
                                        (Lab 3 & 4: Auto-Scaling & Updates)
                                                    │
                                                    ▼
                             [ Secure Secret Injection & HPA Scale Fleet ]
            
```

---

## 🛠️ Repository Roadmap

### [Lab 1: Containerization with Docker](./labs/1_ContainersAndDocker/)
* **Focus:** Packaging legacy applications for modern cloud environments.
* **Key Achievements:** Built optimized multi-layer Docker images for a Node.js runtime, managed local image layers, and configured image pushes to a private cloud registry.
* **Tech Stack:** Docker, IBM Cloud Container Registry.

### [Lab 2: Kubernetes Orchestration](./labs/2_IntroKubernetes/)
* **Focus:** Shifting from single containers to resilient cluster management.
* **Key Achievements:** Authored declarative YAML Deployment configurations to sustain a 3-pod replica set. Integrated internal networking via a ClusterIP service abstraction to load balance request sequences efficiently across healthy application instances.
* **Tech Stack:** Kubernetes, Pods, Deployments, ClusterIP Services.

### [Lab 3: High Availability, Scaling & Rolling Updates](./labs/3_K8sScaleAndUpdate/)
* **Focus:** Maintaining zero-downtime under dynamic scale requirements and version migrations.
* **Key Achievements:** Elastic horizontal scaling to 10 active concurrent application pods. Executed an live, in-production rolling upgrade strategy from version `v1` to `v2` with transient proxy failover monitoring under high traffic load.
* **Tech Stack:** Horizontal Pod Scaling, Rolling Updates (`kubectl set image`), Service Self-Healing.

### [Lab 4: Automated Scaling & Secrets Management](./labs/4_k8-scaling-and-secrets-mgmt/)
* **Focus:** Automated elastic scaling alongside security hardening policies.requirements and version migrations
* **Key Achievements:** Configured automated cluster adjustments via the Horizontal Pod Autoscaler (HPA) responding to traffic demand thresholds. Isolated database authentication assets from source layouts using native Secret configuration models.
* **Tech Stack:** Horizontal Pod Autoscaler (HPA), Kubernetes Secrets, Environment Context Injection.

## 🚀 Module 5: Enterprise Red Hat OpenShift Basics

In this lab, I migrated a local Node.js CRUD application to an enterprise-grade Red Hat OpenShift environment utilizing Source-to-Image (S2I) build pipelines, automated routing services, and deployment lifecycle configurations.

### 🛠️ Key Technical Milestones Achieved:
1. **Source-to-Image (S2I) Compilation**: Configured an automated pipeline that pulled application source code directly from Git, securely managed standard dependency configurations (`npm install`), and pushed the built container directly into the cluster's internal image registry.
2. **Cluster Topology Deployment**: Provisioned and validated a healthy active runtime pod linked to an active routing service mapped to a secure public endpoint.
3. **Infrastructure Declarations**: Extracted and backed up core platform configurations (`Deployment` and `ReplicaSet` specs) tracking built-in memory/CPU boundary limits and progress deadlines.

### 📊 Lab Artifacts & Manifests
* **Live App Endpoint**: [Deployed Application UI Workspace](https://nodejs-ex-git-sn-labs-lamido361.labs-prod-openshift-san-a45631dc5778dc6371c67d206ba9ae5c-0000.us-east.containers.appdomain.cloud/)
* **Cluster Deployment Specification**: [`deployment-nodejs-ex-git.yaml`](./labs/5_openshift-basics/deployment-nodejs-ex-git.yaml)
* **Cluster ReplicaSet Blueprint**: [`replicaset-nodejs-ex-git-7dc754986.yaml`](./labs/5_openshift-basics/replicaset-nodejs-ex-git-7dc754986.yaml)

### 📸 Architecture Visual Proof
#### Active Deployment Ring Topology View
![OpenShift Deployment Topology](./labs/5_openshift-basics/assets/Screenshot%20from%202026-06-25%2017-11-16.png)

#### Successful S2I Build Log Proof
![Build Pipeline Stream Success](./labs/5_openshift-basics/assets/Screenshot%20from%202026-06-25%2017-41-12.png)

#### Live Web Application User Interface
![Live Application Platform UI](./labs/5_openshift-basics/assets/Screenshot%20from%202026-06-25%2018-30-35.png)

---

## 🚀 Key Takeaways
Through this progressive sequence, I engineered reliable application patterns demonstrating key cloud principles: Immutability via Docker, Abstraction via Kubernetes Services, and Elastic Self-Healing Capability & Secrets Decoupling under scale adjustments and secure parameter distribution.