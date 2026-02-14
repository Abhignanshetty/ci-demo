pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Pulling code from GitHub'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ci-mini-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f ci-mini-container || true
                docker run -d --name ci-mini-container -p 5001:5000 ci-mini-app
                '''
            }
        }
    }
}
