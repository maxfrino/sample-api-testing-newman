pipeline {
    agent {
        docker { image 'postman/newman_ubuntu1404' }
    }
    stages {
        stage('Test API') {
            steps {
                sh 'newman run AutomateTestCreateUser.postman_collection.json  -e dev.postman_environment.json --insecure'
            }
        }
    }
}
