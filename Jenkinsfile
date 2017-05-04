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
    SNYK_TOKEN = 'credentials(\'SNYK-TOKEN\')'
  }
}