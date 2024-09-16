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
        always {
            emailext (
                to: 'aryanarora235rja@gmail.com',
                subject: "Build Notification: ${currentBuild.currentResult} - $JOB_NAME #$BUILD_NUMBER",
                body: """Build Status: ${currentBuild.currentResult}
                         Project: $JOB_NAME
                         Build Number: $BUILD_NUMBER
                         Build URL: $BUILD_URL
                         This email is to notify you that the build process has completed."""
            )
        }
    }
}
