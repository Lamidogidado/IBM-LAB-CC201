Lab 1: Containerizing and Deploying a Node.js App
📌 Project Overview
This project demonstrates how to containerize a simple Node.js application using Docker and push the resulting image to the IBM Cloud Container Registry (ICR). This is a foundational step in cloud-native development, ensuring that applications run consistently across different environments.

🛠 Skills Demonstrated
Writing a multi-stage Dockerfile.

Building and tagging Docker images.

Managing images in a remote Cloud Registry.

Using the IBM Cloud CLI (ibmcloud) for container management.

🚀 The Process
1. Local Development
I started with a basic Node.js application (app.js) and defined the environment in a Dockerfile.

2. Building the Image
The image was built locally and tagged for version control:
bash
docker build . -t myimage:v1

3. Verification
I ran the container locally to ensure the port mapping and application logic were correct:
bash
docker run -dp 8080:8080 myimage:v1
curl localhost:8080

4. Pushing to IBM Cloud Registry
To make the image available for cloud deployment (like Kubernetes), I pushed it to the IBM Cloud Container Registry:

Log in to the Registry:

Bash
ibmcloud cr login
Tag the image for the remote repository:

Bash
docker tag myimage:v1 us.icr.io/<my_namespace>/hello-world:1
Push the image:

Bash
docker push us.icr.io/<my_namespace>/hello-world:1