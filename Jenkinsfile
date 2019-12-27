
pipeline {

agent any
    
stages {

  stage ('stage1'){
    steps{
        echo "stage 1 step ${$env:studentname}"
    }

  }
    
    stage ('stage 2')
    {
        steps {
        
            powershell 'write-output "Hello, World !"'
        }
    
    }

  stage ('stage3'){
    steps{
      echo "stage 2 step changes "
    }

  }
    
        stage ('stage 4')
    {
        steps {
        
            powershell 'write-output "Hello, World ! ${env:studentname}"'
        }
    
    }
    
    stage('stage 5')
    {
        environment {
        
                service = powershell(returnStatus: true, script: 'get-service -name ${env:studentname}')
            }
            steps {
          
                powershell 'write-output "$service"'
        // Success!
    }
            
        }
    }

}


