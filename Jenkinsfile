pipeline {
     agent any
     stages {
         stage('Lint HTML') {
             steps {
                 sh 'tidy -q -e *.html'
             }
         }
         stage('Upload to AWS') {
              steps {
                   withAWS(region:'us-east-2',credentials:'AKIA3KD4FW5SZIV7V45S') {
                        s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'peter-pan-bucket-moses')
                   }
              }
         }
     }
}

