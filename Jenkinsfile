pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(credentials:'aws-static') {
        sh 'echo "Uploading"'
        s3Upload(file:'index.html', bucket:'jenkins-aws-static-udacity', path:'index.html')
      }
    }
  }
}
