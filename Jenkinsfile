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
    
     /*stage('Creating self signed certificate using openssl') {
             steps {
   
                 
                  sh 'echo Generate demo rootca key '
                  sh "openssl req -x509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout ${params.CERTIFICATE_COMMON_NAME}.key -out ${params.CERTIFICATE_COMMON_NAME}.pem -subj /C=UK/CN=${params.CERTIFICATE_COMMON_NAME}-root-ca"
                  sh 'echo Generate key and CSR for dem certificate'
                  sh "openssl req -new -nodes -newkey rsa:2048 -out ${params.CERTIFICATE_COMMON_NAME}.csr -subj /C=UK/ST=LONDON/L=LONDON/O=LONDON/CN=${params.CERTIFICATE_COMMON_NAME}"
                  sh 'echo Create certificate using csr and key generated in above steps'
                  sh  'pwd'
                  sh "openssl x509 -req -sha256 -days 1024 -in ${params.CERTIFICATE_COMMON_NAME}.csr -CA ${params.CERTIFICATE_COMMON_NAME}.pem -CAkey ${params.CERTIFICATE_COMMON_NAME}.key -CAcreateserial -extfile domains.ext -out ${params.CERTIFICATE_COMMON_NAME}.crt"
                  sh "echo ${params.CERTIFICATE_PATH}"
                 // sh 'cd params.CERTIFICATE_PATH '
                  sh  'pwd'
                
             }
       }*/
    stage('Creating self signed certificate') {
             steps {
   
                 
                  sh 'echo Creating keystore which contains a private key and a self-signed public key .. '
                  sh "keytool -genkey -keyalg RSA -alias dummy -keystore ${params.CERTIFICATE_COMMON_NAME}.jks -storepass 123123 -validity 1024 -keysize 2048 -dname 'CN=${params.CERTIFICATE_COMMON_NAME}, O=London, L=London, S=London, C=UK, OU=London'"
                  sh 'echo Generate a certificate signing request CSR for above keystore'
                  sh "keytool -certreq -alias dummy -keystore ${params.CERTIFICATE_COMMON_NAME}.jks -file ${params.CERTIFICATE_COMMON_NAME}.csr -storepass 123123"
                  sh 'echo self-signed  X.509 certificate named'
                //  sh  'pwd'
                  sh "keytool -export -alias dummy -keystore ${params.CERTIFICATE_COMMON_NAME}.jks -storepass 123123 -rfc -file ${params.CERTIFICATE_COMMON_NAME}.cer -ext domains.ext"               
               
                 sh 'echo import key store '
                 sh "keytool -importkeystore -srckeystore ${params.CERTIFICATE_COMMON_NAME}.jks -destkeystore ${params.CERTIFICATE_COMMON_NAME}-keystore.p12 -deststoretype PKCS12 -srcalias ${params.CERTIFICATE_COMMON_NAME} -deststorepass 123123 -destkeypass 123123"
                 sh 'echo extract private key '
                 sh 'openssl pkc12 -in ${params.CERTIFICATE_COMMON_NAME}-keystore.p12 -nodes -nocerts -out ${params.CERTIFICATE_COMMON_NAME}-key.pem'
                 sh ' echo Check which certificate is in above Java keystore'
                 sh "keytool -list -v -keystore ${params.CERTIFICATE_COMMON_NAME}.jks"
               
                 sh "echo ${params.CERTIFICATE_PATH}"
                 // sh 'cd params.CERTIFICATE_PATH '
                  sh  'pwd'
                  sh 'cat README.md'
               
                
             }
       }
           
        
        
      } //stages
    
   
  }


   
