pipeline {
    agent any
    parameters {
        choice(name : PersonChoice, choices:['yes', 'no'])
    }

    stages {
        stage('Extract from github') {
            steps {
                git branch: 'main', credentialsId: '9d6b7018-81e2-425a-a324-c389e61b8744', url: 'https://github.com/ShibinChristin/Ecommerce-Management-System.git'
            }
        }
        stage('Compile process') {
            // when {
            //     expression {
            //         params.PersonChoice == 'yes'
            //     }
            // }
            steps {
                sh 'g++ Ecommerce.cpp Merchant.cpp Customer.cpp Courier.cpp main.cpp'
            }
        }
    }
}
