pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/AndreyKhoroshenko/cicd-pipeline/', branch: 'main', credentialsId: 'AndreyKhoroshenko_id')
      }
    stage('Build') {
      agent any
      steps {
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
