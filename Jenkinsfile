pipeline {
  agent any
  stages {
    stage('SCM') {
      steps {
        echo 'This is Demo'
        git(url: 'git@github.com:hrushie/RJTodo', branch: 'jenkins', poll: true, credentialsId: 'e6a8c2f5-1b23-4d61-8e1d-8ba3a4475b5c')
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
 ./gradlew clean assembleQARelease --stacktrace'''
      }
    }
    stage('Test') {
      steps {
        sh './gradlew cleanTest test jacocoTestReport --continue --info'
      }
    }
  }
}