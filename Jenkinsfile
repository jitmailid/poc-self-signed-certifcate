//docker push ${IMAGE}:${VERSION}
pipeline {
  environment {
    /*registry = "gustavoapolinario/docker-test"
    registryCredential = ‘dockerhub’ */
     // CERTIFICATE_COMMON_NAME = "${params.CERTIFICATE_COMMON_NAME}"
     // CERTIFICATE_PATH = "${params.CERTIFICATE_PATH}"
      VALIDATION_COMPLETE = false
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
   
                 
                  sh 'echo hello world'
                  sh "echo ${params.CERTIFICATE_COMMON_NAME}"
                  sh "echo ${params.CERTIFICATE_PATH}"
                 // sh 'cd params.CERTIFICATE_PATH '
                  sh  'pwd'
                
             }
       }
     
           
        
        
      } //stages
    
   
  }


   
