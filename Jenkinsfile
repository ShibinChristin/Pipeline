pipeline {
    agent any
    parameters {
        choice(name : PersonChoice , choices:['yes','no'])
    }

    stages {
        stage('Extract from github') {
            steps {
                git branch: 'main', credentialsId: '9d6b7018-81e2-425a-a324-c389e61b8744', url: 'https://github.com/ShibinChristin/Ecommerce-Management-System.git'
            }
        }
        stage('Compile process') {
            steps {
                script {
                    if ($params.PersonChoice=="yes") {
                        sh 'g++ Ecommerce.cpp Merchant.cpp Customer.cpp Courier.cpp main.cpp'
                    }
                else {
                        echo "Unable to build ${env.BUILD_NUMBER}"
                }
                }
            }
        }
    }
}
