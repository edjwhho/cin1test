#!/usr/bin/env groovy

    agent any
    environment {
        COMPOSE_PROJECT_NAME = "${env.JOB_NAME}-${env.BUILD_ID}"
    }
    stages {
         stage('Build') {
            steps {
                echo 'Building with EH edit...'
                sh 'npm install'
                   }
            }
        
          stage('Test') {
            steps {
                echo 'Testing  with EH edit ...'
                sh 'npm test'
                }
            }
    }
     
    post {
        always {
            sh "docker-compose down -v"
        }
    }
}
