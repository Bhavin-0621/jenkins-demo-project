pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/Bhavin-0621/jenkins-demo-project.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage completed'
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
            mail to: 'your-email@gmail.com',
                 subject: 'Jenkins Build SUCCESS',
                 body: 'Deployment completed successfully.'
        }
        failure {
            mail to: 'your-email@gmail.com',
                 subject: 'Jenkins Build FAILED',
                 body: 'Build or deployment failed. Please check Jenkins logs.'
        }
    }
}

