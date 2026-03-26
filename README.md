🚀 CI/CD Pipeline Project — The Biryani Palace
📌 Overview

This project demonstrates the implementation of a fully automated end-to-end CI/CD pipeline using GitHub, Jenkins, Docker, and AWS EC2.

The objective is to ensure that every code push triggers an automated workflow that builds, containerizes, and deploys the application without any manual intervention.

The application is a Flask-based restaurant website named “The Biryani Palace”, running inside a Docker container on AWS EC2.

🏗️ Architecture
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

This architecture enables:

Continuous Integration (CI)
Continuous Deployment (CD)
Fully automated delivery pipeline
🧰 Technology Stack
Git – Version control
GitHub – Source code hosting
Jenkins – CI/CD automation server
Docker – Containerization platform
AWS EC2 – Cloud compute environment
Flask – Python web framework
📁 Repository Structure
CI-CD-project/

├── app.py
├── requirements.txt
├── Dockerfile
├── Jenkinsfile
└── templates/
    └── index.html
⚙️ CI/CD Pipeline Stages
1. Checkout Source Code
Pulls the latest code from the GitHub repository
2. Build Docker Image
Builds a new Docker image using the Dockerfile
3. Stop Existing Container
Stops and removes the currently running container (if any)
4. Deploy New Container
Runs a new container using the updated image
5. Post-Deployment Logging
Logs success or failure of the pipeline execution
🔄 Automation Flow
GitHub webhook triggers Jenkins on every push
Jenkins executes pipeline automatically
No manual deployment required
🌐 Deployment Details
Hosted on AWS EC2
Application exposed on port 5000
Fully automated deployment pipeline
Zero downtime container replacement (basic level)

Each push to the main branch results in:

Automatic Docker image build
Replacement of existing container
Instant update of the live application
🎯 Key Learnings
Setting up Jenkins on AWS EC2 from scratch
Managing Docker permissions for Jenkins user
Implementing webhook-based automation
Handling cloud resource limitations (disk, swap)
Debugging pipeline failures and Git authentication issues
Designing a repeatable CI/CD workflow
⚠️ Limitations (Current Scope)
No rollback mechanism
No monitoring or alerting setup
No load balancer or high availability
Not production-grade (single EC2 instance)
🚀 Future Improvements
Add Nginx reverse proxy
Implement HTTPS (SSL with Let's Encrypt)
Integrate Prometheus + Grafana monitoring
Use Kubernetes for orchestration
Implement multi-stage Docker builds
Add rollback strategy in Jenkins pipeline
📌 Conclusion

This project demonstrates a practical implementation of a CI/CD pipeline using industry-relevant tools. It reflects real-world DevOps workflows and provides a strong foundation for building production-grade deployment systems.
