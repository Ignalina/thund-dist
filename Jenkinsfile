pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'docker build -f docker/alpine/unchained/Dockerfile .'
      }
    }

  }
}