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
                always {
                    mail to: "${env.EMAIL_TO_NOTIFY}",
                         subject: "Tests Success: ${currentBuild.fullDisplayName}",
                         body: "Unit and integration tests have passed."
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Running Code Analysis stage...'
            }
        }
        
        // Add more stages here if needed
        
    }
}

