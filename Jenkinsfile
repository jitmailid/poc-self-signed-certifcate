//docker push ${IMAGE}:${VERSION}
pipeline {
  environment {
    /*registry = "gustavoapolinario/docker-test"
    registryCredential = ‘dockerhub’ */
      IMAGE = "my-image"
      VERSION = '1.0'
      VALIDATION_COMPLETE = false
      CONTAINER_NAME= "test-helm-chart"
      
  }
  agent any
  stages { 
   stage('Cloning Git') {
      steps {
        git 'https://github.com/jitmailid/poc-self-signed-certifcate.git'
      }
    }
        stage('Build docker image') {
             steps {
                sh '''
                    echo 'hello world'
                    
                '''
             }
       }
     
           
        
        
      } //stage
    
   
  }
}

   
