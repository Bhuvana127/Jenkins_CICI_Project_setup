@Library("my_library") _

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    def config = [
                        url: 'https://github.com/Bhuvana127/maven_calculator_app-main.git',
                        branch: 'main',
                        credentialsId: 'Github_jenkins'
                    ]
                    echo "Starting checkout with config: ${config}"
                    gitCheckout(config)
                    sh '''
                        pwd
                        ls -lrt
                        echo "Inside App repository & calling gitCheckout Library............."
                    '''
                }
            }
        }
        stage('Vulnerability check') {
            steps {
                echo 'Running vulnerability scan........'
                sh '''
                    trivy image --exit-code 1 --severity CRITICAL python:latest
                '''
            }
        }
    }
    post {
        failure {
            echo 'Checkout failed. Check Git configuration or credentials.'
        }
    }
}