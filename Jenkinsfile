pipeline {
    agent any
    environment {
        REPO_URL = 'https://github.com/223127405/jenkins-pipeline-project.git'
        STAGING_SERVER = 'AWS-EC2-Staging'
        PRODUCTION_SERVER = 'AWS-EC2-Production'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven."
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests and integration tests using JUnit and Selenium."
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Analyzing code quality using SonarQube."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Scanning for vulnerabilities using OWASP Dependency Check."
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to staging (AWS EC2)."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on staging."
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to production (AWS EC2)."
            }
        }
    }
    post {
        always {
            emailext (
                to: 'developer@example.com',
                subject: 'Pipeline Status: ${currentBuild.currentResult}',
                body: '''The Jenkins pipeline has completed.
                Build Result: ${currentBuild.currentResult}
                Logs attached.''',
                attachLog: true
            )
        }
    }
}
