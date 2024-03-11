pipeline {
    agent any
    environment {
        GOOGLE_TOKEN=""
    }
    stages {
         stage('Clone Github') {
            steps {
                // Checkout your source code from version control
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
                
                // Deploy the Apigee proxy using the Apigee Maven plugin
                sh "cd templates && mvn apigee-enterprise:deployProxy -Dorg=i8c-apigee-2 -Dtoken=$(GOOGLE_TOKEN) -Denv=default-dev"
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

                
