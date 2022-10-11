pipeline{
    agent any 
    parameters{
        string(name : 'Java-Version', defaultValue : '' , description : "Which java version would you like ?")
        
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages{
        stage("Example"){
        steps{
            echo "Hello $params.Person"
            echo "$params.BIOGRAPHY"
            echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

               
            
        }
    }
    }
}
