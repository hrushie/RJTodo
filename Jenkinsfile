pipeline {
  agent any
  stages {
    stage('SCM') {
      steps {
        echo 'This is Demo'
      }
    }
    stage('Build') {
      steps {
        sh '#send msg'
      }
    }
    stage('Test') {
      steps {
        sh '#Test msg'
      }
    }
  }
}