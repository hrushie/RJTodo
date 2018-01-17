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
        sh '''export ANDROID_HOME=/foo/bar/sdk
#run build
chmod -R 777 .
./gradlew clean assemble --stacktrace
 '''
      }
    }
  }
}