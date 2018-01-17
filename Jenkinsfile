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
        sh '''#run build
chmod -R 777 .
./gradlew clean assemble --stacktrace
 '''
      }
    }
  }
}