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
        stage('Validating the parameters') {
             steps {
   
                 
                  sh 'echo hello world'
                  sh "echo ${params.CERTIFICATE_COMMON_NAME}"
                  sh "echo ${params.CERTIFICATE_PATH}"
                 // sh 'cd params.CERTIFICATE_PATH '
                  sh  'pwd'
                
             }
       }
    
     stage('Creating ') {
             steps {
   
                 
                  sh 'echo hello world'
                  sh "openssl req -X509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout rooca.key -out rootca.pem -subj /C=LONDON/CN=abc-demo-root-ca"
                  sh "openssl req -new -nodes -newkey rsa:2048 -keyout abc-demo.key -out abc-demo.csr -subj /C=LONDON/ST=LONDON/L=LONDON/O=LONDON/CN=abc-demo"
                  sh "echo ${params.CERTIFICATE_PATH}"
                 // sh 'cd params.CERTIFICATE_PATH '
                  sh  'pwd'
                
             }
       }
           
        
        
      } //stages
    
   
  }


   
