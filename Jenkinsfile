pipeline {
    agent any
    environment {
        EMAIL_TO_NOTIFY = 'mchen0201fujiko@gmail.com'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Running Build stage...'
                echo 'Using build automation tool: Maven.'
                echo 'Compiling and packaging the code...'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests stage...'
                echo 'Executing integration tests to ensure various application components interact correctly.'
                echo 'Test automation tools: JUnit for unit testing and JUnit or TestNG for integration testing.'
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
                echo 'Analyzing the code for best practices and standards.'
                echo 'Integrating code analysis tools using Jenkins.'
                echo 'Tools: SonarQube or Checkmarx.'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Running Security Scan stage...'
                echo 'Tools for security scanning: OWASP Dependency-Check or Snyk.'
            }
            post {
                always {
                    mail to: "${env.EMAIL_TO_NOTIFY}",
                         subject: "Tests Success: ${currentBuild.fullDisplayName}",
                         body: "Security Scan tests have passed."
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Running Deploy to Staging stage...'
                echo 'Deploying to a cloud provider - AWS EC2.'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging stage...'
                echo 'Ensuring the application operates as expected in a production-like setting.'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Running Deploy to Production stage...'
                echo 'Deploying to a cloud provider - AWS EC2.'
            }
            post {
                always {
                    mail to: "${env.EMAIL_TO_NOTIFY}",
                         subject: "Tests Success: ${currentBuild.fullDisplayName}",
                         body: "Deploy to Production tests have passed."
                }
        }
        
    }
}

