pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh '''apt npm install
'''
        sh '''chmod +x ./scripts/build.sh
./scripts/build.sh'''
      }
    }

    stage('test') {
      steps {
        sh './scripts/test.sh'
      }
    }

    stage('Build a docker image') {
      steps {
        sh 'docker.build("${env.IMAGE_NAME}:${env.BUILD_NUMBER}")'
      }
    }

  }
}