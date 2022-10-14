pipeline {
    agent any
    parameters {
  choice choices: ['create file', 'Upload file','Rename file','Delete file','Delete workspace'], description: 'Choose an option', name: 'Option'
}
options{
    skipDefaultCheckout()
}
    stages {
        stage('Build') {
            steps{
                script{
                    if(params.Option=="create file"){
                        fileOperations([fileCreateOperation(fileContent: 'This is a sample file created by FileOperation Create', fileName: 'Sample.txt')])
                    }
                    else if(params.Option=="Delete workspace"){
                        cleanWs()
                    }
                }
            }
            
}
    }
}