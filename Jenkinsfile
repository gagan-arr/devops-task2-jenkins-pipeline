pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pulls the code from GitHub
                git branch: 'main', url: 'https://github.com/gagan-arr/devops-task2-jenkins-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Builds Docker image
                sh 'docker build -t nodejs-demo-app .'
            }
        }

        stage('Install Dependencies & Test') {
            steps {
                sh 'npm install'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Runs your app in Docker container
                sh 'docker run -d -p 3000:3000 nodejs-demo-app'
            }
        }
    }
}
