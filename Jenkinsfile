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
    
     stage('Creating self signed certificate') {
             steps {
   
                 
                  sh 'echo Generate demo rootca key '
                  sh "openssl req -x509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout rootca.key -out rootca.pem -subj /C=UK/CN=abc-demo-root-ca"
                  sh 'echo Generate key and CSR for dem certificate'
                  sh "openssl req -new -nodes -newkey rsa:2048 -keyout abc-demo.key -out abc-demo.csr -subj /C=UK/ST=LONDON/L=LONDON/O=LONDON/CN=abc-demo"
                  sh 'echo Create certificate using csr and key generated in above steps'
                  sh "openssl x509 -req -new -sha256 -days 1024 -in abc-demo.csr -CA rootca.pem -CAkey abc-demo.key -CAcreateserial -extfile domains.ext -out ${params.CERTIFICATE_PATH}.crt"
                  sh "echo ${params.CERTIFICATE_PATH}"
                 // sh 'cd params.CERTIFICATE_PATH '
                  sh  'pwd'
                
             }
       }
           
        
        
      } //stages
    
   
  }


   
