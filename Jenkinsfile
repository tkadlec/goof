pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh '''node -v
npm prune
npm install'''
        sh '''snyk auth
snyk test'''
      }
    }
    stage('Build') {
      steps {
        sh 'snyk monitor'
      }
    }
  }
  environment {
    SNYK_TOKEN = '8b761a35-c6b8-47bc-8c80-44ec3e7133b8'
  }
}