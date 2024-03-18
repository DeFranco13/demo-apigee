pipeline {
    agent any
    environment {
        GOOGLE_TOKEN="azdazjhdazefdezfa8256189Bd"
    }
    stages {
         stage('Clone Github') {
            steps {
                git 'https://github.com/DeFranco13/demo-apigee'
            }
        }
        stage('Maven check'){
            steps {
                sh "mvn -v"
            }
        }
        stage('Package'){
            steps{
                sh "mvn package -DdeployUser -Dorg=i8c-apigee-2"
            }
        }
    }
        
    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

                
