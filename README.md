# SIT737 – Task 6.2C: Interacting with Kubernetes

This task extends the calculator microservice developed in Task 6.1P by enabling interaction with the Kubernetes cluster using `kubectl` commands and updating the microservice to include new functionality and UI improvements.

## Project Overview

This Node.js calculator microservice supports the following operations:

- Addition
- Subtraction
- Multiplication
- Division
- **Modulo (NEW)**

The service has been containerised with Docker, deployed to a local Kubernetes cluster, and exposed using a Kubernetes `NodePort` service. Traffic is forwarded from a local port to the Kubernetes service using `kubectl port-forward`.

## Features Added in 6.2C

### New Functionality:
- **Modulo operation (%)** has been added to the backend and is fully functional.

### UI Enhancements:
- A new Modulo button was added to the calculator interface.
- Styling improved using Bootstrap to enhance the visual experience.

## Build and Push Docker Image

1. Build the image:
-  docker build -t `<user-name>/<image-name>` .

2. Push the image to Docker Hub:
-  docker push `<user-name>/<image-name>`

## Kubernetes Deployment

1. Deploy the App
- kubectl apply -f deployment.yaml

2. Verify resources
- kubectl get pods

## Port Forward to Access App
kubectl port-forward service/calculator-service 8080:3000


Access the application via http://localhost:8080


