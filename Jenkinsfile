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
                        echo"Creating a smaple file"
                        fileOperations([fileCreateOperation(fileContent: 'This is a sample file created by FileOperation Create', fileName: 'Sample.txt')])
                    }
                    else if(params.Option=="Delete workspace"){
                       echo"Deleting workspce"
                        cleanWs()
                    }
                    else if(params.Option=="Upload file"){
                        cleanWs()
                        // Get file using input step, will put it in build directory
print "=================Please upload your property file here ====================="
def fileBase64 = input message: 'Please provide a file', parameters: [base64File('file')]
node {
    withEnv(["fileBase64=$fileBase64"]) {
        sh 'echo $fileBase64 | base64 -d > myFile.txt'
        // powershell '[IO.File]::WriteAllBytes("myFile.txt", [Convert]::FromBase64String($env:fileBase64))'
    }
    // do something with the file stored in ./myFile.txt
}
                    }
                }
            }
            
}
    }
}