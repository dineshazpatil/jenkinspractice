
pipeline {

agent any
parameters {
  string defaultValue: 'myname', description: '', name: 'test1', trim: true
}
    
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
          
                powershell 'write-output "${service}"'
        // Success!
    }
      
                
        }
  
    stage ('stage 6')
  {
    input{
		message "Press Ok to continue"
		submitter "user1,user2"
		parameters {
			string(name:'username', defaultValue: 'user', description: 'Username of the user pressing Ok')
		}
	    
    	}
    
      steps{
        //echo "User: ${username} said OK"
        powershell 'write-output ${env:username}'
      }
  
  }
  
    


// use full refrence
//http://jenkins3.southindia.cloudapp.azure.com:8080/pipeline-syntax/globals
//http://groovy-lang.org/semantics.html
// mail to: 'devops@acme.com',
    //subject: "Job '${JOB_NAME}' (${BUILD_NUMBER}) is waiting for input",
    //body: "Please go to ${BUILD_URL} and verify the build"
// ${YOUR_JENKINS_URL}/directive-generator.

//https://jenkins.io/doc/pipeline/steps/pipeline-input-step/
}
}
