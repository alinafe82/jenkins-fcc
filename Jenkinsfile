pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/alinafe82/jenkins-fcc', branch: 'dev')
      }
    }

    stage('') {
      steps {
        sh 'ls -la'
      }
    }

  }
  environment {
    env = 'dev'
  }
}