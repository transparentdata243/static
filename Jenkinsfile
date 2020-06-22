pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
          sh 'tidy -q -e *.html'
        }
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-east-1', credentials:'aws-static') {
          sh 'echo "Uploading test scan detection"'
          s3Upload(file:'index.html', bucket:'jenkins-aws-static-udacity', path:'index.html')
        }
      }
    }
  }
}
