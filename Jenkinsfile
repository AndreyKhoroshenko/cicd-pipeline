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

    stage('Push') {
      steps {
        sh '''docker.withRegistry(\'https://registry.hub.docker.com\', \'docker_hub_creds_id\') 
  {
    def app = docker.image("${env.IMAGE_NAME}:${env.BUILD_NUMBER}")
    app.push("${env.BUILD_NUMBER}")
    app.push("latest")
  }'''
      }
    }

  }
}