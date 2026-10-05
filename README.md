# 🚀 Task 2 – Jenkins CI/CD Pipeline

## Elevate Labs – DevOps Internship

### 📌 Project Overview

This project demonstrates the implementation of a basic **CI/CD pipeline using Jenkins**.

The pipeline automatically retrieves the application source code from GitHub and executes the required build and execution steps through Jenkins.

The objective of this task is to understand how Jenkins can be used to automate software development and deployment workflows.

---

## 🛠️ Technologies Used

- **Jenkins** – CI/CD automation server
- **Git & GitHub** – Source code management
- **Node.js** – Application runtime
- **npm** – Node.js package manager
- **Git Bash** – Command-line environment
- **Windows** – Development environment

---

## 📂 Project Structure

```text
Task-2-Jenkins/
│
├── app.js
├── package.json
├── Jenkinsfile
└── README.md
```

---

## 🔄 CI/CD Workflow

The Jenkins pipeline follows this basic workflow:

```text
Developer
    ↓
GitHub Repository
    ↓
Jenkins
    ↓
Clone / Checkout Source Code
    ↓
Install Dependencies
    ↓
Build / Test
    ↓
Run Application
    ↓
Pipeline Success
```

---

## ⚙️ Jenkins Pipeline

The Jenkins pipeline is defined using a `Jenkinsfile`.

The pipeline contains stages for:

1. **Checkout** – Retrieves the source code from GitHub.
2. **Install Dependencies** – Installs the required Node.js packages.
3. **Build** – Performs the application build step.
4. **Test** – Executes the available tests.
5. **Run Application** – Runs the Node.js application.

---

## 📄 Jenkinsfile

```groovy
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'YOUR_GITHUB_REPOSITORY_URL'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                bat 'echo Build stage completed'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Run Application') {
            steps {
                bat 'node app.js'
            }
        }
    }

    post {
        success {
            echo 'Jenkins Pipeline completed successfully!'
        }

        failure {
            echo 'Jenkins Pipeline failed. Check the console output.'
        }
    }
}
```

> **Note:** Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual GitHub repository URL before using this Jenkinsfile.

---

## 🧪 Application Verification

The Node.js application was executed successfully through the Jenkins pipeline.

Example output:

```text
Hello from Jenkins
```

This confirms that Jenkins successfully executed the Node.js application.

---

## 🔧 Jenkins Setup

### Step 1 – Start Jenkins

Start the Jenkins service and open the Jenkins dashboard.

Example:

```text
http://localhost:8080
```

### Step 2 – Create a New Pipeline

1. Open Jenkins.
2. Click **New Item**.
3. Enter the project name.
4. Select **Pipeline**.
5. Click **OK**.

### Step 3 – Configure Pipeline

Under the Pipeline section:

```text
Definition:
Pipeline script from SCM

SCM:
Git

Repository URL:
YOUR_GITHUB_REPOSITORY_URL

Branch:
*/main

Script Path:
Jenkinsfile
```

Save the configuration.

### Step 4 – Build the Pipeline

Click:

```text
Build Now
```

Jenkins will retrieve the source code from GitHub and execute the pipeline stages.

---

## ✅ Pipeline Result

After successful execution, Jenkins displays:

```text
Finished: SUCCESS
```

The successful pipeline confirms that the Jenkins CI/CD workflow is working correctly.

---

## 📚 What I Learned

Through this task, I learned:

- What Jenkins is and why it is used in DevOps.
- How Jenkins automates CI/CD workflows.
- How to create a Jenkins Pipeline.
- How to connect Jenkins with GitHub.
- How to use a `Jenkinsfile`.
- How Jenkins executes pipeline stages.
- How to install Node.js dependencies using npm.
- How to execute a Node.js application through Jenkins.
- How to troubleshoot pipeline failures using Jenkins Console Output.
- How source-code changes can be integrated into an automated CI/CD workflow.

---

## 🎯 Key DevOps Concepts

### Continuous Integration (CI)

Continuous Integration automatically integrates and validates code changes whenever developers push changes to the source-code repository.

### Continuous Delivery / Deployment (CD)

Continuous Delivery/Deployment automates the process of preparing or deploying an application after successful integration and testing.

### Jenkins

Jenkins is an open-source automation server widely used to implement CI/CD pipelines.

### Jenkinsfile

A `Jenkinsfile` stores the pipeline configuration as code, allowing the CI/CD process to be version-controlled along with the application source code.

---

## 📌 Task Outcome

The objective of this task was successfully completed by creating and executing a Jenkins-based CI/CD pipeline.

The project demonstrates the integration of:

```text
GitHub + Jenkins + Node.js
```

and shows how Jenkins can automate application execution through a pipeline.

---

## 👩‍💻 Author

**Amitha Sri Kambathula**

DevOps / DevSecOps Learner

---

## 🔗 Repository

GitHub Repository:

**Add your GitHub repository URL here**

```text
YOUR_GITHUB_REPOSITORY_URL
```