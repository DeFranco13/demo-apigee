pipeline {
    agent any
    environment {
        GOOGLE_TOKEN=""
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
                /*
                
                Credentials
                
                node {
                    withCredentials([
                        usernamePassword(credentialsId: 'nexus-creds',usernameVariable: 'NEXUS_USERNAME',passwordVariable: 'NEXUS_PASSWORD')
                                    ]) 
                        {
                        echo 'My credentials: $NEXUS_USERNAME:$NEXUS_PASSWORD'
                        }
                    }
                */
                
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

                
