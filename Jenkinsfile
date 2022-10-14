pipeline {
    agent any
    parameters {
  choice choices: ['create file', 'Upload file','Rename file','Delete file','Delete workspace'], description: 'Choose an option', name: 'Option'
    base64File 'THEFILE'
}
options{
    // timestamps()
    skipDefaultCheckout()
}
    stages {
        stage('Build') {
            steps{
                script{
                    if(params.Option=="create file"){
                        echo"Creating a smaple file"
                        fileOperations([fileCreateOperation(fileContent: 'This is a sample file created by FileOperation Create', fileName: 'Sample.txt')])
                    }
                    else if(params.Option=="Delete workspace"){
                       echo"Deleting workspce"
                        cleanWs()
                    }
                    else if(params.Option=="Upload file"){
                        cleanWs()
                        withFileParameter('THEFILE') {
                            sh 'cat $THEFILE'                        
                        // Get file using input step, will put it in build directory
}
    }
                    }
                }
            }
            
}
}