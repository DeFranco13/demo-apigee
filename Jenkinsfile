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
        stage('Deploy Apigee Proxy') {
            steps {
                
                sh "mvn package -Dname=TestProxy -Denv=default-dev && mvn apigee-enterprise:deploy -Pgoogleapi -Dorg=i8c-apigee-2 -Dtoken=${GOOGLE_TOKEN} -Dname=TestProxy -Denv=default-dev"
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

                
