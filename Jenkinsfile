pipeline{
    agent {
        docker{
            image "ubuntu:latest"
        }
    }
    stages{
        stage("Update Docker"){
            steps{
                sh "sudo apt-get update"
            }
        }
    }
}