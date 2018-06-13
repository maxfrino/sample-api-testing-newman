pipeline {
    agent {
        docker { image 'postman/newman_ubuntu1404' }
    }
    stages {
        stage('Test API') {
            steps {
                sh 'newman --version;'
                sh 'newman run /var/jenkins_home/postman/AutomateTestCreateUser.postman_collection.json  -e /var/jenkins_home/postman/tty-dev.postman_environment.json --insecure'
            }
        }
    }
}
