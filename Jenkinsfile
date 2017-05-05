pipeline {
  agent any
  stages {
    stage('Check from Github') {
      steps {
        git(url: 'https://github.com/fcenedes/restbook2.git', branch: 'master', credentialsId: '96cdb75a-1a28-435d-8722-fa642c6a31d6')
      }
    }
  }
}