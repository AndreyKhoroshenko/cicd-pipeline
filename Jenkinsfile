pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''chmod +x \\ scripts/build.sh\\
script ./scripts/build/sh'''
      }
    }

    stage('Test') {
      steps {
        sh 'script ./scripts/test.sh'
      }
    }

    stage('Docker') {
      steps {
        sh 'docker build -t andreykhoroshenko/cicd .'
      }
    }

  }
}