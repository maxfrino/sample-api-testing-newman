pipeline {
    agent {
        docker { image 'postman/newman_ubuntu1404:2.1.2' }
    }
    stages {
        stage('Test API') {
            steps {
                sh 'newman -c AutomateTestCreateUser.postman_collection.json -e dev.postman_environment.json'
            }
        }
    }
}
