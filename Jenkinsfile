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
                    emailext (
                        attachLog: false,
                        to: 'aryanarora235rja@gmail.com',
                        subject: "Unit and Integration Tests Successful - Jenkins",
                        body: "The Unit and Integration Tests were successful. Check logs for more details."
                    )
                }
                failure {
                    emailext (
                        attachLog: true,
                        to: 'aryanarora235rja@gmail.com',
                        subject: "Unit and Integration Tests Failed - Jenkins",
                        body: "The Unit and Integration Tests failed. Check logs for more details."
                    )
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
                    emailext (
                        attachLog: false,
                        to: 'aryanarora235rja@gmail.com',
                        subject: "Security Scan Successful - Jenkins",
                        body: "The Security Scan was successful. Check logs for more details."
                    )
                }
                failure {
                    emailext (
                        attachLog: true,
                        to: 'aryanarora235rja@gmail.com',
                        subject: "Security Scan Failed - Jenkins",
                        body: "The Security Scan failed. Check logs for more details."
                    )
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
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
