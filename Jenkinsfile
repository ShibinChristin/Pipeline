pipeline{
    agent any
    stages{
        stage("Extract from github"){
            steps{
                git branch: 'main', credentialsId: '9d6b7018-81e2-425a-a324-c389e61b8744', url: 'https://github.com/ShibinChristin/Ecommerce-Management-System.git'
            }
        }
        stage("Compile process"){
            try{
                sh "g++ Ecommerce.cpp Merchant.cpp Customer.cpp Courier.cpp main.cpp"
                catch(Err){
                    echo "Build number ${env.BUILD_NUMBER} failed"
                }
            }

        }
    }
}