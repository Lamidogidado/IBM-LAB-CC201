# Lab 5: Red Hat OpenShift Container Platform Basics

## 📌 Project Overview
This lab explored enterprise cluster orchestration using the Red Hat OpenShift Platform. Shifting focus away from bare infrastructure manifests, I deployed an application using OpenShift's developer-focused automated engineering pipelines.

## 🛠️ Skills Demonstrated
* **Source-to-Image (S2I) Pipelines:** Automated container generation directly from raw source code loops without writing structural Dockerfiles.
* **OpenShift Web Console Management:** Utilized unified topology maps to orchestrate resources, monitor real-time streaming build logs, and manage service routing infrastructure visually.
* **Enterprise Cluster Operations:** Navigated platform mechanics using the OpenShift `oc` CLI toolchain to manage isolated user namespaces.

## 🚀 The Process & Architecture

Instead of compiling images locally and pushing them to external container registries, OpenShift abstracts the assembly workflow entirely via an independent builder workflow:

```text
[ Git Codebase ] ───> [ S2I Builder Engine ] ───> [ Compiling Runtime Dependencies ]
                                                              │
[ Public Route URL ] <─── [ Pod Deployment ] <─── [ Internal Cluster Registry ]