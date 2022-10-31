pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'python manage.py jenkins --enable-coverage'
      }
    }

  }
}