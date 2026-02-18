**Overview**
__________________
This project demonstrates the design and implementation of an end-to-end CI/CD pipeline using GitHub, Jenkins, Docker, and AWS EC2.

The primary objective was to build a fully automated deployment workflow where every code push triggers a build, containerization process, and deployment to a cloud server — without any manual intervention.

The deployed application is a Flask-based restaurant website ("The Biryani Palace") running inside a Docker container on AWS EC2.

**Architecture**
__________________
Deployment Workflow
Developer
   ↓
Git Push (GitHub)
   ↓
Webhook Trigger
   ↓
Jenkins Pipeline
   ↓
Docker Image Build
   ↓
Container Replacement
   ↓
Live Application on AWS EC2


_This architecture ensures continuous integration and automated deployment upon every push to the main branch.
_

**Technology Stack:**
________________________

Git – Version control

GitHub – Source code hosting

Jenkins – CI/CD automation server

Docker – Containerization platform

AWS EC2 – Cloud compute environment

Flask – Python web framework

**Repository Structure**
____________________________
CI-CD-project/

│
├── app.py

├── requirements.txt

├── Dockerfile

├── Jenkinsfile

└── templates/

    └── index.html
    

**CI/CD Pipeline Stages**
___________________________

The Jenkins pipeline consists of the following stages:

Checkout Source Code – Pull latest changes from GitHub

Build Docker Image – Create updated container image

Stop Existing Container – Safely terminate running instance

Deploy New Container – Run updated image on EC2

Post-Deployment Logging – Log success/failure

The pipeline is automatically triggered through GitHub webhook integration.

Deployment Details

Hosted on AWS EC2

Application exposed on port 5000

Fully automated container replacement on every push

Each commit to the main branch results in:

Automatic Docker image rebuild

Replacement of the previous running container

Immediate update of the live application

**Key Learnings**
____________________

Configuring Jenkins on AWS EC2 from scratch

Managing Docker daemon permissions for Jenkins user

Handling disk and swap limitations in cloud environments

Implementing webhook-based automated deployment

Debugging Git authentication and pipeline failures

Designing a repeatable and reliable deployment workflow
