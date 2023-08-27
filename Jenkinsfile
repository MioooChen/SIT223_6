pipeline {
    agent any
    environment {
        EMAIL_TO_NOTIFY = 'mchen0201fujiko@gmail.com'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Running Build stage...'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests stage...'
            }
            post {
                success {
                    emailext subject: "Tests Success: ${currentBuild.fullDisplayName}",
                             body: "Unit and integration tests have passed.",
                             to: "${env.EMAIL_TO_NOTIFY}",
                             attachLog: true
                }
                failure {
                    emailext subject: "Tests Failure: ${currentBuild.fullDisplayName}",
                             body: "Unit and integration tests have failed. Please review the logs.",
                             to: "${env.EMAIL_TO_NOTIFY}",
                             attachLog: true
                }
            }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis stage...'
            }
        }
        
        
        
    
    }
}
