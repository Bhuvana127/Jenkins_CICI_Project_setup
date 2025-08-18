@Library("gitCheckout") _

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    def config = [
                        url: 'https://github.com/Bhuvana127/Hello-world-app-JAVA.git',
                        branch: 'main',
                        credentialsId: 'token_github'
                    ]
                gitCheckout(config)    
                sh '''
                    ls -lrt
                    echo "Inside App repository & calling gitCheckout Library............."
                '''                          
                } 
            }
        }
    }
}    