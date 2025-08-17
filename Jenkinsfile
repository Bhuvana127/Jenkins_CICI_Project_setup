pipeline {
    agent any

    environment {
        // Define environment variables here
        BUILD_ENV = 'production'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Example: sh 'npm install' or 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example: sh 'npm test' or 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Example: sh './deploy.sh' or use Jenkins deploy plugins
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // Example: clean workspace, send notifications, etc.
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
