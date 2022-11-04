pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'python manage.py jenkins --enable-coverage'
      }
    }

    stage('Testing') {
      parallel {
        stage('Admin App') {
          steps {
            sh 'python manage.py test admins'
          }
        }

        stage('Students App') {
          steps {
            sh 'python manage.py test students'
          }
        }

        stage('Teachers App') {
          steps {
            sh 'python manage.py test teachers'
          }
        }

      }
    }

    stage('Deliver') {
      steps {
        echo 'Finish'
      }
    }

  }
}