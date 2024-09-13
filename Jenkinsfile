pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path specified by the environment variable."
                echo "Compiling the code and generating any necessary artifacts."
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests."
                echo "Running integration tests."
            }
            post {
                success {
                    emailext attachLog: true,
                    to: 'aryanarora235rja@gmail.com',
                    subject: "Unit and Integration Tests Successful",
                    body: "Unit and Integration tests completed successfully. Please check the attached log for details."
                }
                failure {
                    emailext attachLog: true,
                    to: 'aryanarora235rja@gmail.com',
                    subject: "Unit and Integration Tests Failed",
                    body: "Unit and Integration tests failed. Please check the attached log for details."
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Checking the quality of the code using a code analysis tool."
            }
        }

        stage('Security Scan') {
            steps {
                echo "Identifying vulnerabilities using a security scanning tool."
            }
            post {
                success {
                    emailext attachLog: true,
                    to: 'aryanarora235rja@gmail.com',
                    subject: "Security Scan Successful",
                    body: "Security scan completed successfully. Please check the attached log for details."
                }
                failure {
                    emailext attachLog: true,
                    to: 'aryanarora235rja@gmail.com',
                    subject: "Security Scan Failed",
                    body: "Security scan failed. Please check the attached log for details."
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production environment."
            }
        }
    }

    post {
        success {
            emailext attachLog: true,
            to: 'aryanarora235rja@gmail.com',
            subject: "Pipeline Successful - Jenkins",
            body: "The Jenkins pipeline completed successfully. Please check the attached log for details."
        }
        failure {
            emailext attachLog: true,
            to: 'aryanarora235rja@gmail.com',
            subject: "Pipeline Failed - Jenkins",
            body: "The Jenkins pipeline failed. Please check the attached log for details."
        }
    }
}
