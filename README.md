# SIT737 – Task 6.2C: Interacting with Kubernetes

## Prerequisites

Make sure the following tools are installed and configured before proceeding:

- Docker Desktop (with Kubernetes enabled)
- `kubectl` CLI (included with Docker Desktop)
- Docker Hub account
- Codebase and deployment files from Task 6.1P

## Step-by-Step Instructions

### Step 1: Verify Application Deployment

Run the following commands to ensure your application is properly deployed:

- kubectl get pods
- kubectl get services

### Step 2: Port Forwarding (Required)
kubectl port-forward service/calculator-service 8080:3000

### Step 3: Modify the Application (Part II)
1. New Feature: Modulo Operation (%)
- A new /modulo route was added in the backend.
- Logic for performing modulo and error handling (e.g., divide by zero) was implemented.
- Winston logger was used to track modulo usage.

2. UI Enhancements:
- A new "Modulo (%)" button was added to the calculator UI.
- Bootstrap layout and styles were adjusted to maintain consistency and usability.
  
### Step 4: Rebuild and Push Docker Image
- docker build -t mayura1994/calculator-microservice-6.2c .
- docker push mayura1994/calculator-microservice-6.2c

### Step 5: Update deployment.yaml
Update the image name in your deployment configuration:

containers:
  - name: calculator
    image: mayura1994/calculator-microservice-6.2c

Apply the changes:
kubectl apply -f deployment.yaml

### Step 6: Re-Access Updated App in Browser
kubectl port-forward service/calculator-service 8080:3000


Access via http://localhost:8080


