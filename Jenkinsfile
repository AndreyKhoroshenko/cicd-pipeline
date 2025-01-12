pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh '''chmod +x /scripts/build.sh
script ./scripts/build/sh'''
      }
    }

    stage('Test') {
      agent any
      steps {
        sh 'script ./scripts/test.sh'
      }
    }

    stage('Docker') {
      agent any
      steps {
        sh 'docker build -t andreykhoroshenko/cicd .'
      }
    }

    stage('Push') {
      agent any
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