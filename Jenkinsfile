//docker push ${IMAGE}:${VERSION}
pipeline {
  environment {
    /*registry = "gustavoapolinario/docker-test"
    registryCredential = ‘dockerhub’ */
      CERTIFICATE_COMMON_NAME = "${params.CERTIFICATE_COMMON_NAME}"
      CERTIFICATE_PATH = "${params.CERTIFICATE_PATH}"
      //VALIDATION_COMPLETE = false
     // CONTAINER_NAME= "test-helm-chart"
      
  }
  agent any
  stages { 
   stage('Cloning Git') {
      steps {
        git 'https://github.com/jitmailid/poc-self-signed-certifcate.git'
      }
    }
        stage('Validating the p') {
             steps {
    if (CERTIFICATE_COMMON_NAME == null) {
    error("Build failed because of CERTIFICATE_COMMON_NAME BLANK")
     }
                sh '''
                    echo 'hello world'
                    
                '''
             }
       }
     
           
        
        
      } //stages
    
   
  }


   
