pipeline {
    agent any
    environment {
        TESTING_ENVIROMENT = '6.2C pipeline'
        PRODUCTION_ENVIROMENT = 'Aryan Arora'
        RECIPIENT_EMAIL = 'aryanarora235rja@gmail.com'  // Updated email for notifications
    }
    stages {
        stage('Build') {
            steps {
                sleep(3)
                echo "Building code using Maven..."
            }
        }
        stage('Test') {
            steps {
                echo "Running Unit tests and integration from TestNG..."
            }
            post {
                always {
                    archiveArtifacts artifacts: '**/test_logs.txt', allowEmptyArchive: true
                    script {
                        mail to: "${env.RECIPIENT_EMAIL}",
                            subject: "Test Stage ${currentBuild.result}: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                            body: "The Test stage has ${currentBuild.result}. Please check the logs attached.",
                            attachments: 'test_logs.txt'
                    }
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Performing Code analysis using SonarQube..."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Performing Security Scan using OWASP..."
            }
            post {
                always {
                    archiveArtifacts artifacts: '**/security_scan_logs.txt', allowEmptyArchive: true
                    script {
                        mail to: "${env.RECIPIENT_EMAIL}",
                            subject: "Security Scan Stage ${currentBuild.result}: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                            body: "The Security Scan stage has ${currentBuild.result}. Please check the logs attached.",
                            attachments: 'security_scan_logs.txt'
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying to staging in AWS CLI..."
            }
        }
        stage('Integration tests on staging') {
            steps {
                echo 'Running integration tests on staging with Selenium...'
            }
        }
    }
    post {
        always {
            echo "Pipeline completed."
        }
    }
}
