pipeline {
    agent any
    stages {        
        stage('Initialize'){
            steps{
                script {
                    def dockerHome = tool 'myDocker'
                    def nodejsHome  = tool 'myNodejs'
                    env.PATH = "${dockerHome}/bin:${nodejsHome}/bin:${env.PATH}"
                }
            }
        }
        stage('Test API') {
            steps {
                sh 'pwd'
                sh 'ls -la'
                //sh 'newman -u https://www.getpostman.com/collections/631643-f695cab7-6878-eb55-7943-ad88e1ccfd65-JsLv;'
                sh 'docker run --name newman postman/newman_ubuntu1404:2.1.2 newman -c AutomateTestCreateUser.postman_collection.json -e dev.postman_environment.json'
            }
        }
    }
    post {
        success {
            echo 'The Pipeline success :)'
            sh 'docker rm newman'
        }
        failure { 
            script {
                echo 'The Pipeline failed :('
                sh 'docker rm newman'
            }
        }
    }
}
