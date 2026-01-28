pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build completed'
            }
        }

        stage('Deploy') {
            steps {
                sh 'chmod +x deploy.sh'
                sh './deploy.sh'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'bhavinpanchal33@gmail.com',
                subject: "SUCCESS: ${JOB_NAME} #${BUILD_NUMBER}",
                body: "Build Successful\nJob: ${JOB_NAME}\nBuild: ${BUILD_NUMBER}"
            )
        }
        failure {
            emailext(
                to: 'bhavinpanchal33@gmail.com',
                subject: "FAILED: ${JOB_NAME} #${BUILD_NUMBER}",
                body: "Build Failed\nJob: ${JOB_NAME}\nBuild: ${BUILD_NUMBER}"
            )
        }
    }
}

