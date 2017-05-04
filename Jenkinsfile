pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh '''node -v
npm prune
npm install'''
        sh 'snyk test'
      }
    }
    stage('Build') {
      steps {
        sh 'snyk monitor'
      }
    }
  }
  environment {
    SNYK_TOKEN = '2fc81e36-5881-4288-b8d4-5b86993b7e08'
  }
}