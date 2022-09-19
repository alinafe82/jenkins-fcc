pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git 'https://github.com/alinafe82/jenkins-fcc'
      }
    }

  }
  environment {
    env = 'dev'
  }
}