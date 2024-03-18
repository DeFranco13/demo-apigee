pipeline {
    agent any
    environment {
        GOOGLE_TOKEN="azdazjhdazefdezfa8256189Bd"
        USERNAME=""
        PASSWORD=""
    }
    stages {
         stage('Setup') {
            steps {
                git 'https://github.com/DeFranco13/demo-apigee'
                sh "mvn -v"
            }
        }
        stage('Package'){
            steps{
                sh "mvn -f Mock-v1/pom.xml package -P test "
            }
        }
        stage('Install'){
            steps{
                sh "mvn -f Mock-v1/pom.xml install -P test -Dbearer={GOOGLE_TOKEN}"
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

                
