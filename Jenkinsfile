pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t jenkins-cicd-app .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
                bat 'docker run --rm jenkins-cicd-app npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'

                bat '''
                    docker rm -f jenkins-cicd-container
                    docker run -d --name jenkins-cicd-container -p 3000:3000 jenkins-cicd-app
                '''
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD Pipeline failed. Check the console output.'
        }
    }
}