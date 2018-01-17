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
        sh '''#run python script to get updated configurations
cd app
chmod -R 777 .
./autoGenerateConfiguration.py
cd ..

#run build
chmod -R 777 .
 ./gradlew clean assembleDEVDebug --stacktrace
 '''
      }
    }
  }
}