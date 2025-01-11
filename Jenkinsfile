pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('build') {
      steps {
        sh '''npm install
chmod +x ./scripts/build.sh
./scripts/build.sh'''
      }
    }

  }
}