pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region:'eu-west-2',credentials:'aws-static') {
          sh 'echo "Upload to AWS bucket"'
          s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'temp-jenkins-project-bucket')
        }
      }
    }
  }
}
