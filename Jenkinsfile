pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging application...'
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'

            emailext(
                subject: "SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The Jenkins pipeline completed successfully.",
                to: "kollapunikitha.23.cse@anits.edu.in"
            )
        }

        failure {
            echo 'Pipeline failed.'

            emailext(
                subject: "FAILURE: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "The Jenkins pipeline failed. Please check the Jenkins console output.",
                to: "kollapunikitha.23.cse@anits.edu.in"
            )
        }
    }
}
