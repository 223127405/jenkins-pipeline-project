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
                    emailext attachLog: false,  // Log attachment disabled
                    to: 'aryanarora235rja@gmail.com',
                    body: "Unit and Integration Tests were successful. Log is available at $JENKINS_HOME/jobs/$JOB_NAME/builds/lastSuccessfulBuild/log",
                    subject: "Unit and Integration Tests Successful - Jenkins"
                }
                failure {
                    emailext attachLog: false,  // Log attachment disabled
                    to: 'aryanarora235rja@gmail.com',
                    body: "Unit and Integration Tests failed. Log is available at $JENKINS_HOME/jobs/$JOB_NAME/builds/lastFailedBuild/log",
                    subject: "Unit and Integration Tests Failed - Jenkins"
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
                    emailext attachLog: false,  // Log attachment disabled
                    to: 'aryanarora235rja@gmail.com',
                    body: "Security Scan was successful. Log is available at $JENKINS_HOME/jobs/$JOB_NAME/builds/lastSuccessfulBuild/log",
                    subject: "Security Scan Successful - Jenkins"
                }
                failure {
                    emailext attachLog: false,  // Log attachment disabled
                    to: 'aryanarora235rja@gmail.com',
                    body: "Security Scan failed. Log is available at $JENKINS_HOME/jobs/$JOB_NAME/builds/lastFailedBuild/log",
                    subject: "Security Scan Failed - Jenkins"
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
}
