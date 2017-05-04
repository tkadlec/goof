pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh 'snyk test'
      }
    }
    stage('Build') {
      steps {
        sh 'snyk monitor'
      }
    }
  }
}