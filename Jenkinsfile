pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'test -f index.html'
                sh 'test -f Dockerfile'
                sh 'test -f Jenkinsfile'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the application...'
                sh 'grep -q "Jenkins" index.html'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t jenkins-docker-assignment:latest .'
            }
        }
    }
}
