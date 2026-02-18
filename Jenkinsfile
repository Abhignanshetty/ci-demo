
pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Abhignashetty/ci-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop flask || true
                docker rm flask || true
                docker run -d -p 5000:5000 --name flask flask-demo
                '''
            }
        }
    }
}
