pipeline {
    agent any
    environment {
        
    }
    stages {
         stage('Clone Github') {
            steps {
                // Checkout your source code from version control
                git 'https://github.com/DeFranco13/demo-apigee'
            }
        }
        stage('Install Maven') {
            steps {
                script {
                    // Install Maven using the tool installer
                    def mvnHome = tool 'Maven'
                    env.PATH += ":${mvnHome}/bin"
                }
            }
        }
        stage('Build Maven') {
            steps {
                // Use the installed Maven to execute Maven commands
                sh 'mvn clean install'
            }
        }
        stage('Deploy Apigee Proxy') {
            steps {
                
                // Deploy the Apigee proxy using the Apigee Maven plugin
                sh "cd templates && ${MAVEN_HOME}/bin/mvn apigee-enterprise:deployProxy -Dorg=${org} -Denv=${env} -Dusername=${username} -Dpassword=${password} -Doptions=none"
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

                
