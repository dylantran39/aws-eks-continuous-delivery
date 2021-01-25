# Amazon Elastic Kubernetes Service With CodeBuild for Continuous Delivery (CD)

Reference: https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html

## Setup

```bash
# Build docker image
docker build -t nodejswebapp .

# Run docker image to create container
docker run -it nodejswebapp /bin/bash

# Login ECR AWS
aws ecr get-login

# Tag image into ECR AWS
docker tag nodejswebapp:latest 012345678912.dkr.ecr.us-west-2.amazonaws.com/nodejswebapp:latest

# Push image into ECR AWS
docker push 012345678912.dkr.ecr.us-west-2.amazonaws.com/nodejswebapp:latest

# Create cluster
eksctl create cluster --name nodejs-eks --region us-west-2 --nodegroup-name standard-nodes --node-type t3.medium --version 1.17 --managed

# Get cluster
eksctl get cluster

# Get nodes
kubectl get nodes

# Get all
kubectl get all

# Get ns
kubectl get ns

# Apply deployment
kubectl apply -f deployment.yaml

# Apply service
kubectl apply -f service.yaml

# Get pods
kubectl -n kube-system get pods

# Get pods wide
kubectl get pods -o wide

# Get nodes wide
kubectl get nodes -o wide

# Delete cluster
eksctl delete cluster --name nodejs-eks

# Get service
kubectl get service

# Get deployment
kubectl get deployment
```
