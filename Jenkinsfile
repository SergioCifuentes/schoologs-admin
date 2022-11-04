pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'python schoologs/manage.py runserver'
      }
    }

    stage('Testing') {
      parallel {
        stage('Admin App') {
          steps {
            sh 'python schoologs/manage.py test admins'
          }
        }

        stage('Students App') {
          steps {
            sh 'python schoologs/manage.py test students'
          }
        }

        stage('Teachers App') {
          steps {
            sh 'python schoologs/manage.py test teachers'
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
