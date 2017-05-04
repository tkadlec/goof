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
        sh '''snyk protect
snyk monitor'''
      }
    }
  }
  environment {
    SNYK_TOKEN = credentials('SNYK_TOKEN')
  }
}