pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging EC2...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running tests on staging...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production EC2...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            emailext (
                subject: "SUCCESS: Build ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Good news! Your build completed successfully.",
                to: '1999manmeetkaur@gmail.com'
            )
        }
        failure {
            emailext (
                subject: "FAILURE: Build ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Something went wrong. Please check the logs.",
                to: '1999manmeetkaur@gmail.com'
            )
        }
    }
}
