# Amazon Elastic Container Service (Amazon ECS)

## Amazon Elastic Container Service (Amazon ECS) is a fully managed container orchestration service. 

- ECS helps you run Docker containers on EC2 machines
- ECS is complicated, and made of:
    1. “ECS Core”: Running ECS on user-provisioned EC2 instances
    2. Fargate: Running ECS tasks on AWS-provisioned compute (serverless)
    3. EKS: Running ECS on AWS-powered Kubernetes (running on EC2)
    4. ECR: Docker Container Registry hosted by AWS
- ECS & Docker are very popular for microservices

<div style="text-align:center"><img src="images/ecs_logo.png" /></div>

---
## AWS ECS – Use cases
### Run microservices
- Ability to run multiple docker containers on the same machine
- Easy service discovery features to enhance communication
- Direct integration with Application Load Balancers
- Auto scaling capability
### Run batch processing / scheduled tasks
- Schedule ECS containers to run on On-demand / Reserved / Spot instances
### Migrate applications to the cloud
- Dockerize legacy applications running on premise
- Move Docker containers to run on ECS

<div style="text-align:center"><img src="images/ecs.png" /></div>

---
## AWS ECS - Components
<div style="text-align:center"><img src="images/ecs_architecture.png" /></div>

## Cluster
### An Amazon ECS cluster is a logical grouping of tasks or services. If you are running tasks or services that use the EC2 launch type, a cluster is also a grouping of container instances.

## Service
### Amazon ECS allows you to run and maintain a specified number of instances of a task definition simultaneously in an Amazon ECS cluster. This is called a service. If any of your tasks should fail or stop for any reason, the Amazon ECS service scheduler launches another instance of your task definition to replace it and maintain the desired count of tasks in the service depending on the scheduling strategy used.

## Task Definition
### A task definition is required to run Docker containers in Amazon ECS
