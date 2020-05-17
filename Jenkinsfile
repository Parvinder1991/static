pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }
stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-east-2',credentials:'0ce8e502-d225-4c20-b721-8f34c699d7c9') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-udacity-123')
                  }
              }
         }
     }

}
