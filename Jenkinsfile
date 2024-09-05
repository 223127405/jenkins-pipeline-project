pipeline {
    agent any
    environment {
        REPO_URL = 'https://github.com/223127405/jenkins-pipeline-project.git'
        STAGING_SERVER = 'AWS-EC2-Staging'
        PRODUCTION_SERVER = 'AWS-EC2-Production'
    }
    stages {
        // Your pipeline stages go here...
    }
    post {
        always {
            emailext (
                to: 'aryanarora235rja@gmail.com',
                subject: 'Jenkins Pipeline Build',
                body: 'The Jenkins pipeline has completed successfully. Check the Jenkins UI for logs.',
                attachLog: false  // Disable log attachment
            )
        }
    }
}
