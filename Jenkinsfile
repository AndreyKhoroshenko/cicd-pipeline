pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        sh 'git(url: \'https://github.com/AndreyKhoroshenko/cicd-pipeline.git\', branch: \'main\''
      }
    }

    stage('Build') {
      steps {
        sh 'chmod +x ./scripts/build.sh'
      }
    }

  }
}