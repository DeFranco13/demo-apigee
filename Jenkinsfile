pipeline {
    agent any
    environment {
        GOOGLE_TOKEN="azdazjhdazefdezfa8256189Bd"
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
                sh "mvn -f Mock-v1/pom.xml install -P test -Dbearer=ya29.a0Ad52N3_Sf0A6FhTMIltaP5UWm3jzf4VojEPAPwk6a5CFXruim5-wnZurUY9Qn6WZCaIu3UNGRB_ougnq3ecY-eMX15-SwL56DTF0xBsjehqnZq_oxB0sFobBOQGkZpV-u42dKt6UhmIBijt5ntmJYmJH8KgdSaEi-t3ZC7xMJguFGHVC5QPwUN3h4PckghtxvbKGDTJEtDQMbyMwXTtqje5uKyIGMrYn6un4T37Uq5LZcMIiebGuQlJiI7gZeoOPzO8FZAkLyzFZC9mTAtQKr3es8ChGVeqh1S5thduJP8w7UsvDxoy81T3ANs78sfs6V3QK-6BBZNJ56bFZapljuUeXQrji2iKhvKsvd75pPyXTQk-aXaEJ4NmKramSV9p0NF5rVEFYoGHDn5qtOeI9TCKTmeGofAaCgYKAQMSARESFQHGX2Mi9c0pUgFhrFhZI0opVRdEvg0421"
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

                
