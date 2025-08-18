@Library("my_library") _

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    def config = [
                        url: 'https://github.com/Bhuvana127/Hello-world-app-JAVA.git',
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
    }
    post {
        failure {
            echo 'Checkout failed. Check Git configuration or credentials.'
        }
    }
}