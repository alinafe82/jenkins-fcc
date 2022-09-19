pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/alinafe82/jenkins-fcc', branch: 'dev')
      }
    }

    stage('error') {
      parallel {
        stage('File contents') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Front-End Unit Test') {
          steps {
            sh 'cd curriculum-front && npm i && npm run test:unit'
          }
        }

      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -f curriculum-front/Dockerfile . -t fuze365/curriculum-front'
      }
    }

    stage('Docker login') {
      steps {
        sh '''docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD
'''
      }
    }

    stage('Docker push') {
      steps {
        sh 'docker push fuze365/curriculum-front:latest'
      }
    }

  }
  environment {
    env = 'dev'
  }
}