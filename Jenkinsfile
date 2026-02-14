
stage('Docker Login') {
    steps {
        withCredentials([usernamePassword(
            credentialsId: 'docker-hub-creds',
            usernameVariable: 'DOCKER_USER',
            passwordVariable: 'DOCKER_PASS'
        )]) {
            sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
        }
    }
}
stage('Push Image') {
    steps {
        sh '''
        docker tag ci-mini-app abhignanshetty/ci-mini-app:latest
        docker push abhignanshetty/ci-mini-app:latest
        '''
    }
}
