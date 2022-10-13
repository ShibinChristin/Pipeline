pipeline {
    agent any
    parameters {
  choice choices: ['yes', 'no'], description: 'Yes or no to the choice', name: 'PersonChoice'
}
    stages {
        stage('Extract from github') {
            steps {
                git branch: 'main', credentialsId: '9d6b7018-81e2-425a-a324-c389e61b8744', url: 'https://github.com/ShibinChristin/Ecommerce-Management-System.git'
            }
        }
        stage('Compile process') {
            when {
                expression {
                    params.PersonChoice == 'yes'
                }
            } 
            steps {
                 fileOperations([fileCreateOperation(fileContent: 'Hello file operation', fileName: 'Ecommerce-Management-System/hello.txt')])        
                sh 'g++ Ecommerce.cpp Merchant.cpp Customer.cpp Courier.cpp main.cpp'
            }
        }
    }
}
