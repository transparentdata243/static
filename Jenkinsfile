pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-east-1', credentials:'aws-static') {
          sh 'echo "Uploading"'
          s3Upload(file:'index.html', bucket:'jenkins-aws-static-udacity', path:'index.html')
        }
      }
    }
  }
}
