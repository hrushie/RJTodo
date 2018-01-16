pipeline {
  agent any
  stages {
    stage('demo') {
      parallel {
        stage('demo') {
          steps {
            echo 'This is Demo'
          }
        }
        stage('Build') {
          steps {
            build 'Android'
          }
        }
      }
    }
  }
}