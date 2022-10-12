pipeline{
    agent {
        docker{
            image "ubuntu:latest"
        }
    }
    stages{
        stage("Update Docker"){
            steps{
                sh "apt-get update"
            }
        }
    }
}