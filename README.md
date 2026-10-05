# 🚀 Task 2 – Jenkins CI/CD Pipeline with Docker

## Elevate Labs – DevOps Internship

---

## 📌 Project Overview

This project demonstrates the implementation of a CI/CD pipeline using **Jenkins, Docker, GitHub, and Node.js**.

The application source code is maintained in a GitHub repository. Jenkins automatically retrieves the source code and executes the CI/CD pipeline.

##The pipeline performs the following operations:

```text
GitHub
   ↓
Jenkins
   ↓
Checkout SCM
   ↓
Build Docker Image
   ↓
Test Application
   ↓
Deploy Docker Container
   ↓
Application Running
   ↓
Pipeline Success

The main objective of this task is to understand how Jenkins can automate the software build, testing, and deployment process using Docker.

🎯 OBJECTIVES:
- Understand Jenkins and CI/CD concepts.
- Integrate Jenkins with GitHub.
- Create a Jenkins Pipeline using a Jenkinsfile.
- Build a Docker image through Jenkins.
- Test the Node.js application.
- Deploy the application using Docker.
- Verify the running Docker container.
- Verify the deployed application through a browser.
- Understand Jenkins Console Output and pipeline stages.
- Troubleshoot pipeline failures.

🛠️ TECHNOLOGIES USED:
Technology-Purpose
Jenkins-CI/CD automation
Docker-Containerization and deployment
Git-Version control
GitHub-Source code repository
Node.js-Application runtime
npm-Node.js package manager
JavaScript-Application development
Git Bash-Command-line environment
Windows-Development environment


🔄 CI/CD PIPELINE WORKFLOW:
                 Developer
                     ↓
              GitHub Repository
                     ↓
                  Jenkins
                     ↓
               Checkout SCM
                     ↓
             Build Docker Image
                     ↓
              Test Application
                     ↓
            Deploy Docker Container
                     ↓
             Node.js Application
                     ↓
              localhost:3000
                     ↓
             Pipeline SUCCESS



📂 PROJECT STRUCTURE:
jenkins-cicd-task/
│
├── .gitignore
├── Dockerfile
├── Jenkinsfile
├── README.md
├── app.js
├── package.json
│
└── screenshots/
    ├── Docker-Container.png
    ├── Jenkins-Console.png
    ├── Jenkins-Dashboard.png
    ├── Jenkins-Pipeline.png
    └── application.png

⚙️ JENKINS PIPELINE STAGES:
The Jenkins pipeline consists of the following stages.
1. Checkout SCM:
Jenkins retrieves the latest application source code from the GitHub repository.
GitHub → Jenkins

The repository used for this project is:
https://github.com/iamamitha16/jenkins-cicd-task.git

2. Build:
Jenkins builds a Docker image using the project's Dockerfile.
The Docker image is created using:
docker build -t jenkins-cicd-app .

This packages the Node.js application into a Docker image.

3. Test:
After the Docker image is successfully created, Jenkins tests the application inside a temporary Docker container.
docker run --rm jenkins-cicd-app npm test

The configured test command performs a JavaScript syntax check:
node --check app.js

If the test succeeds, Jenkins continues to the deployment stage.

4. Deploy:
After successful Build and Test stages, Jenkins deploys the application using Docker.
The existing container is removed if necessary:
docker rm -f jenkins-cicd-container

Then the application container is started:
docker run -d --name jenkins-cicd-container -p 3000:3000 jenkins-cicd-app

The application is therefore deployed inside a Docker container.

5. Post Actions:
After all pipeline stages complete successfully, Jenkins displays:
CI/CD Pipeline completed successfully!

The Jenkins build finishes with:
Finished: SUCCESS

🐳 DOCKER IMPLEMENTATION:
Docker is used to containerize and deploy the Node.js application.
#Build Docker Image
docker build -t jenkins-cicd-app .

#Run Docker Container
docker run -d --name jenkins-cicd-container -p 3000:3000 jenkins-cicd-app

#Check Running Containers
docker ps

##The running container is:
jenkins-cicd-container

##The application port mapping is:
3000:3000

###This makes the application available on:
http://localhost:3000

🧪 APPLICATION TESTING:
The application is tested during the Jenkins pipeline.
#The test command is:
npm test

#The test performs a JavaScript syntax check:
node --check app.js

A successful test allows the Jenkins pipeline to continue to deployment.

🌐 APPLICATION VERIFICATION:
After the Docker container is successfully deployed, the application can be accessed using:
http://localhost:3000

#The application displays:
Hello from Jenkins CI/CD Pipeline!

This confirms that the Node.js application was successfully deployed and is running inside the Docker container.
🔧 Jenkins Configuration
Step 1 – Start Jenkins:
Jenkins was started locally and accessed through:
http://localhost:8080

Step 2 – Create Jenkins Pipeline:
1. Open Jenkins Dashboard.
2. Click New Item.
3. Enter the project name.
4. Select Pipeline.
5. Click OK.
Step 3 – Configure Pipeline
The Jenkins job uses:
Definition:
Pipeline script from SCM

SCM:
Git

Repository:
https://github.com/iamamitha16/jenkins-cicd-task.git

Branch:
*/main

Script Path:
Jenkinsfile

The Jenkinsfile stored in the GitHub repository defines the pipeline.

▶️ Running the Pipeline
From the Jenkins project dashboard, the pipeline can be executed using:
Build Now

Jenkins then retrieves the source code and executes the stages sequentially:
Checkout SCM
      ↓
Build
      ↓
Test
      ↓
Deploy
      ↓
Post Actions
      ↓
SUCCESS

📊 PIPELINE VERIFICATION:
The Jenkins Pipeline Overview confirms that the following stages completed successfully:
Checkout SCM    ✓
Build           ✓
Test            ✓
Deploy          ✓
Post Actions    ✓

The Jenkins Console Output also confirms:

##CI/CD Pipeline completed successfully!

Finished: SUCCESS

📸 Screenshots / Evidence:
1. Jenkins Dashboard:
The Jenkins dashboard shows the created Jenkins-CICD-Task pipeline and successful builds.
 
2. Jenkins Pipeline Stages:
The Pipeline Overview shows the successful execution of:
Checkout SCM → Build → Test → Deploy → Post Actions

 
3. Jenkins Console Output:
The Jenkins Console Output demonstrates the Docker image build, application testing, Docker deployment, and successful pipeline completion.
 
4. Docker Container:
The Docker container created during deployment is running successfully with port 3000 mapped to the host machine.
 
5. Application Verification:
The deployed Node.js application is successfully accessible through the browser at:
http://localhost:3000



 
📚 What I Learned;
Through this task, I learned:
- What Jenkins is and how it is used in DevOps.
- How Jenkins automates CI/CD workflows.
- How to create a Jenkins Pipeline.
- How to use a Jenkinsfile.
- How to integrate Jenkins with GitHub.
- How Jenkins retrieves source code from GitHub.
- How to build Docker images through Jenkins.
- How to test an application inside Docker.
- How to deploy an application using Docker.
- How to verify running Docker containers.
- How to troubleshoot Jenkins pipeline failures.
- How to use Jenkins Console Output for troubleshooting.
- How CI/CD automates application delivery.

🎯 Key DevOps Concepts:
Continuous Integration
Continuous Integration involves integrating source-code changes and automatically building and testing the application.
Continuous Delivery / Deployment
Continuous Delivery and Deployment automate the process of delivering or deploying an application after successful build and testing stages.
Jenkins
Jenkins is an automation server commonly used to implement CI/CD pipelines.
Jenkinsfile
A Jenkinsfile stores the Jenkins pipeline configuration as code. It allows the CI/CD process to be maintained together with the application source code.
Docker
Docker packages an application and its required environment into a container, making the application easier to build and run consistently.

📌 Task Outcome:
The Jenkins CI/CD pipeline was successfully created and executed.
The project demonstrates the integration of:
GitHub + Jenkins + Docker + Node.js

The successful pipeline performed:
Checkout SCM
      ↓
Build
      ↓
Test
      ↓
Deploy
      ↓
Post Actions

The Docker container was successfully deployed and the application was verified through:
http://localhost:3000

The application displayed:
Hello from Jenkins CI/CD Pipeline!

This demonstrates a practical Jenkins-based CI/CD workflow using Docker.

🔗 GitHub Repository:
https://github.com/iamamitha16/jenkins-cicd-task

⭐ Conclusion:
This task provided hands-on experience with Jenkins, GitHub, Docker, Node.js, and CI/CD.
The implementation demonstrated how source code can be retrieved from GitHub, built into a Docker image, tested, deployed as a Docker container, and verified through a browser using an automated Jenkins pipeline.