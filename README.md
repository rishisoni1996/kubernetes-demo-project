# Kubernetes Demo Project

## Overview

This repository contains examples and instructions for setting up a Kubernetes cluster, deploying a simple Node.js application, and deploying a React web application. The goal is to provide a hands-on experience with Kubernetes features like deployment, scaling, service creation, and rolling updates.

## Prerequisites

Ensure you have the following tools installed before starting:

- [Kubernetes](https://kubernetes.io/docs/tasks/tools/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)

## Getting Started

1. Install Kubernetes by following the [official documentation](https://kubernetes.io/docs/tasks/tools/).

2. Install Minikube by following the [Minikube installation guide](https://minikube.sigs.k8s.io/docs/start/).

3. Start Minikube:

   ```bash
   minikube start
   ```

4. Open the Kubernetes dashboard:

   ```bash
   minikube dashboard
   ```

## Node.js Application Example

1. Deploy a simple Node.js application:

   ```bash
   kubectl create deployment node-app --image=rishidocker123/server:1.0
   ```

2. Expose the deployment as a LoadBalancer service:

   ```bash
   kubectl expose deployment node-app --type=LoadBalancer --port=4000
   ```

3. Scale the deployment to 4 replicas:

   ```bash
   kubectl scale deployment node-app --replicas=4
   ```

4. Access the application using Minikube service:

   ```bash
   minikube service node-app
   ```

5. Stop the application to see no downtime:

   ```bash
   http://localhost:<port>/exit
   ```

## React Web Application Example

1. Deploy a simple React web application:

   ```bash
   kubectl create deployment my-react --image=rishidocker123/sample:1.0
   ```

2. Expose the deployment as a LoadBalancer service:

   ```bash
   kubectl expose deployment my-react --port=3000 --type=LoadBalancer
   ```

3. View logs of a pod:

   ```bash
   kubectl logs <pod_name>
   ```

4. Describe a pod for detailed information:

   ```bash
   kubectl describe pod <pod_name>
   ```

5. rollout new update with a new image:

   ```bash
   kubectl set image deployment my-react sample=rishidocker123/sample:1.1
   ```

6. Monitor the rolling update:

   ```bash
   kubectl rollout status deployment my-react
   ```

7. Rollback to the previous version:

   ```bash
   kubectl rollout undo deployment my-react
   ```

This repository serves as a guide for exploring Kubernetes features. Feel free to experiment, modify, and extend the examples based on your learning needs. Happy Kubernetes hacking!
