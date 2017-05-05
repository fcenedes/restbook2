pipeline {
  agent any
  stages {
    stage('Check from Github') {
      steps {
        git(url: 'https://github.com/fcenedes/restbook2.git', branch: 'master', credentialsId: '96cdb75a-1a28-435d-8722-fa642c6a31d6', changelog: true)
      }
    }
    stage('Package') {
      steps {
        sh 'cd *.parent/ && mvn initialize clean package'
      }
    }
    stage('Build Docker image') {
      steps {
        sh 'cd *.parent/ && mvn initialize docker:build docker:push'
        echo 'Image has been uploaded to Azure container Registry'
      }
    }
  }
}