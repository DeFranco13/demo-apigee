pipeline {
    agent any
    environment {
        // Define the Maven installation name
        MAVEN_HOME = tool name: 'Maven', type: 'maven'
    }
    stages {
         stage('Checkout') {
            steps {
                // Checkout your source code from version control
                git 'https://github.com/DeFranco13/demo-apigee'
            }
        }
        stage('Build') {
            steps {
                // Use the installed Maven to execute Maven commands
                sh "${MAVEN_HOME}/bin/mvn clean install"
            }
        }
    }
}

                
