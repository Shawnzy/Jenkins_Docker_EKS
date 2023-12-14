# Java Application CI/CD Pipeline with Jenkins, Docker, and AWS EKS

## Overview
This repository contains a Jenkins pipeline for continuous integration and deployment of a Java application. The pipeline automates building the application with Maven, testing, creating a Docker image, pushing/storing the Docker Iamge in the cloud (Dockerhub or AWS ECR), and deploying it to an AWS Elastic Kubernetes Service (EKS) cluster.

### Pipeline Workflow
1. **Trigger**: Triggered on new commits to all branches except the `jenkins-jobs` branch.
2. **Increment Version**: Increases the App Version number
3. **Build**: Uses Maven to build the Java application.
4. **Dockerize**: Creates a Docker image of the application.
5. **Push Image**: Pushes the Docker image to AWS ECR or Docker Hub.
6. **Deploy**: Uses `kubectl` to deploy the image to AWS EKS.
7. **Update `jenkins-jobs` Branch**: Pushes the latest code to the `jenkins-jobs` branch.

## Prerequisites
- Jenkins server with required plugins (e.g., Maven, Docker, Kubernetes)
- Docker and Maven installed on the Jenkins server
- Access to AWS ECR or Docker Hub for storing Docker images
- Access to an AWS account with an EKS cluster set up
- Required credentials configured in Jenkins for Docker, AWS, and GitHub

## Setup and Configuration
1. **Jenkins Configuration**: 
   - Ensure Jenkins has plugins for Maven, Docker, and Kubernetes.
   - Configure credentials in Jenkins for GitHub, AWS, and Docker Hub/ECR.
   
2. **AWS EKS Cluster**:
   - Ensure the EKS cluster is set up and `kubectl` is configured to interact with it.

3. **Docker Hub/ECR Repository**:
   - Set up a Docker repository on Docker Hub or AWS ECR.


## Contributions
Contributions to this pipeline are welcome. Please follow the standard pull request process.
