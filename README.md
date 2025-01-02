Node.js Application with Jenkins CI/CD, Docker, and Kubernetes
This repository demonstrates how to deploy a Node.js application using Jenkins for Continuous Integration (CI) and Continuous Deployment (CD), Docker for containerization, and Kubernetes (Minikube) for orchestration.

**Prerequisites**

Jenkins – Installed and running.
Docker – Installed on the Jenkins server for building images.
Kubernetes (Minikube) – Installed for local Kubernetes clusters.
GitHub Account – For repository and Jenkins integration.
Node.js and npm – Installed for the application.

Steps to Set Up

**1. Node.js Application Setup**
Created a basic Node.js application.
Installed dependencies such as express for the web server.
Added a basic package.json with scripts and dependencies.

**2. Jenkins Setup**
Installed Jenkins on the server and created a pipeline job.
Integrated Jenkins with the GitHub repository for version control.
Configured Jenkins to use Docker for building Node.js images.

**3. Docker Configuration**
Created a Dockerfile to build the Node.js application image.
Enabled Docker BuildKit for faster builds and better control.
Configured Jenkins to use Docker in pipeline steps to build and test the image.

**4. Pipeline Configuration (Jenkinsfile)**
Checkout: Pulled the latest code from GitHub using checkout scm.
Build: Built the Docker image using docker.build().
Test: Ran tests inside the Docker container using Mocha.
Deploy: Applied the Kubernetes deployment configuration (kubectl apply -f kubernetes-deployment.yml) to deploy the app to Minikube.

**5. Kubernetes Setup**
Set up Minikube for local Kubernetes clusters.
Created a kubernetes-deployment.yml for defining the application deployment on Kubernetes.
Configured the kubeconfig to allow Jenkins to communicate with Kubernetes via kubectl.

**6. Authentication with Kubernetes**
Ensured the Kubernetes cluster is accessible using kubectl on the Jenkins server.
Integrated Jenkins with Minikube's kubeconfig file using the kubeconfig credentials plugin.

**7. Testing and Deployment**
Verified the build process, ensuring Docker images were built correctly.
Ran tests within the Docker container to ensure that the Node.js app was functioning properly.
Deployed the application to Minikube and confirmed the deployment using kubectl.
