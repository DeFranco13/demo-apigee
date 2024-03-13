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
        stage('Make Package env'){
            steps{
                sh "mkdir -p /var/jenkins_home/workspace/Demo/target"
            }
        }
        stage('Install'){
            steps{
                sh "mvn install -Papigee -Dapigee.config.options=create"
            }
        }
        stage('Package proxy'){
            steps{
                sh "mvn package -Dname=TestProxy -Denv=default-dev"
            }
        }
        stage('Deploy Apigee Proxy') {
            steps {
                sh "mvn apigee-enterprise:deploy -Pgoogleapi -Dorg=i8c-apigee-2 -Dtoken=${GOOGLE_TOKEN} -Dname=TestProxy -Denv=default-dev"
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

                
