pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                
                sh 'mvn clean package'
            }
        }
        stage('Deploy to CloudHub') {
            steps {
               
                sh 'mvn clean deploy -DmuleDeploy'
            }
        }
    }
    post {
        success {
            // Notify on successful deployment
            echo 'Mule application deployed successfully to CloudHub'
        }
        failure {
            // Notify on deployment failure
            echo 'Failed to deploy Mule application to CloudHub'
        }
    }