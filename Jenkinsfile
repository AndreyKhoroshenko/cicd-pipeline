pipeline {
  agent any
  stages {
    stage('build') {
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

  }
}