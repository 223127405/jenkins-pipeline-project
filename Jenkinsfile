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
                echo "Starting the Build: Fetching code from ${env.REPO_URL}"
                echo "Building the code using Maven... (this is a simulated build step)"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running Unit Tests using JUnit."
                echo "Running Integration Tests using Selenium."
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Performing Code Analysis with SonarQube."
                echo "Checking code quality and standards."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Initiating Security Scan with OWASP Dependency Check."
                echo "Scanning for vulnerabilities."
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to the staging environment: ${env.STAGING_SERVER}."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running Integration Tests on the Staging Environment."
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to the production environment: ${env.PRODUCTION_SERVER}."
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
                Logs attached.

                - Build Stage: ${currentBuild.rawBuild.getAction(hudson.model.ResultAction)?.getResult() ?: "N/A"}
                - Test Stage: ${currentBuild.rawBuild.getAction(hudson.tasks.junit.TestResultAction)?.getResult() ?: "N/A"}
                - Code Analysis: Code analysis completed.
                ''',
                attachLog: true
            )
        }
    }
}
