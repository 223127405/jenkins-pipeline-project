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
        success {
            emailext to: 'aryanarora235rja@gmail.com',
                     subject: "Build SUCCESS - $JOB_NAME Build #$BUILD_NUMBER",
                     body: """Project: $JOB_NAME
                              Build Number: $BUILD_NUMBER
                              Status: SUCCESS
                              Timestamp: ${new Date()}
                              Logs: $BUILD_URL/console

                              This build completed successfully.
                           """
        }
        failure {  
            emailext to: 'aryanarora235rja@gmail.com',
                     subject: "Build FAILURE - $JOB_NAME Build #$BUILD_NUMBER",
                     body: """Project: $JOB_NAME
                              Build Number: $BUILD_NUMBER
                              Status: FAILURE
                              Timestamp: ${new Date()}
                              Logs: $BUILD_URL/console

                              The build failed. Please review the logs for further details.
                           """
        }
    }
}
