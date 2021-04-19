//docker push ${IMAGE}:${VERSION}
pipeline {
  environment {
    
    CERTIFICATE_COMMON_NAME = "${params.CERTIFICATE_COMMON_NAME}"
    CERTIFICATE_PATH = "${params.CERTIFICATE_PATH}"
      
      
      
  }
  agent any
  stages { 
   stage('Creating keystore') {
      steps {
        git 'https://github.com/jitmailid/ranjit-helmchart-testing.git'
      }
    }
        stage('Generate a certificatee signing request') {
             steps {
                sh '''
                
                    keytool -genkey -keyalg RSA -alias dummy -keystore dummy.jks -validity 1024 -keysize 2048 -dname "CN=dummy, O=London, L=London, S=London, C=UK, OU=London"
                    
                '''
             }
       }
      stage('Generate self-signed certificate'){
          steps{
            
           sh '''                 
                  keytool -certreq -alias dummy -keystore dummy.jks -file dummy.csr -storepass 123123                 
                  
              ''' 
                
           
          }
      }
   
      stage('Generic validation of helm chart'){
       
       steps{
       
         sh '''
         
         keytool -export -alias dummy -keystore dummy.jks -storepass 123123 -rfc -file dummy.cer -ext domains.ext
         
         '''

         }
               } 
           
        
        
      } //stage
    
   
  }
}
