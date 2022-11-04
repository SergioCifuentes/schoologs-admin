pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker-compose up'
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
        echo 'End'
      }
    }

  }
}