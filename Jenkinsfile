pipeline {
    agent {
        docker { image 'node:7-alpine' }
    }
    stages {
        stage('Test API') {
            steps {
                sh 'node --version'
            }
        }
    }
}
