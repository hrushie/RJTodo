pipeline {
  agent any
  stages {
    stage('SCM') {
      parallel {
        stage('SCM') {
          steps {
            echo 'This is Demo'
          }
        }
        stage('Checkout') {
          steps {
            sh '''echo "*******************Updating submodule*************************"
MCDARCH_DIR=${WORKSPACE}
MCDAPPCORE_DIR="${MCDARCH_DIR}/libraries/android-mcd-core-app"
MCDUIKIT_DIR="${MCDARCH_DIR}/libraries/android-mcd-core-app/libraries/android-mcd-uikit"
MCDCONNECT_DIR="${MCDARCH_DIR}/libraries/android-mcd-core-app/libraries/android-gma-sdk-sapient"

echo "*************Checking out McDAppARCH Repository*****************"
cd "${MCDARCH_DIR}"
git checkout test_pipeline
git gc --prune=now
git clean -fdx
git pull

echo "*************Checking out McDAppCore Repository*****************"
cd "${MCDAPPCORE_DIR}"
git checkout  develop
git gc --prune=now
git clean -fdx
git pull

echo "*************Checking out McDUIKit Repository*****************"
cd "${MCDUIKIT_DIR}"
git checkout  develop
git gc --prune=now
git clean -fdx
git pull

echo "*************Checking out McDonaldsSDK Repository*****************"
cd "${MCDCONNECT_DIR}"
git checkout  feature/GMA-5.x
git gc --prune=now
git clean -fdx
git pull'''
          }
        }
      }
    }
    stage('Build') {
      steps {
        sh '''
#run build
./gradlew clean assembleQARelease
 '''
      }
    }
  }
}