pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh '''node -v
npm prune
npm install
npm test'''
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