pipeline {
    agent any

    stages {
        stage('Test Email') {
            steps {
                echo 'Testing email sending in Jenkins.'
            }
        }
    }

    post {
        always {
            emailext (
                to: 'aryanarora235rja@gmail.com',  // Replace with your email address
                subject: "Jenkins Test Email - Pipeline ${currentBuild.fullDisplayName}",
                body: "This is a test email from Jenkins. The pipeline job has finished with status: ${currentBuild.currentResult}.",
                attachLog: true
            )
        }
    }
}
