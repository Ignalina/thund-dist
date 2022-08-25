pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'podman build -f docker/alpine/unchained/Dockerfile .'
      }
    }

  }
}