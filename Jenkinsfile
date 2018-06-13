pipeline {
    agent {
        docker { image 'node:7-alpine' }
    }
    stages {
        stage('Test API') {
            steps {
                sh 'node --version'
                sh 'npm install newman --global;'
                sh 'newman run /var/jenkins_home/postman/AutomateTestCreateUser.postman_collection.json  -e /var/jenkins_home/postman/tty-dev.postman_environment.json --insecure'
            }
        }
    }
}
