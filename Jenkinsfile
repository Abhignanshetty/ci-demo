pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code pulled from GitHub'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ci-mini-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run --rm ci-mini-app'
            }
        }
    }
}
