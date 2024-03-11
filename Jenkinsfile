pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Your build steps here
                sh 'echo "Building..."'
            }
        }
        stage('Test') {
            steps {
                // Your test steps here
                sh 'echo "Testing..."'
            }
        }
        stage('Deploy') {
            steps {
                // Your deployment steps here
                sh 'echo "Deploying..."'
            }
        }
    }
    post {
        success {
            // Actions to take if pipeline succeeds
            echo 'Pipeline succeeded!'
        }
        failure {
            // Actions to take if pipeline fails
            echo 'Pipeline failed!'
        }
    }
}

                
