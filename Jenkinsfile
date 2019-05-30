pipeline {
  agent none
  stages {
    stage('clone') {
      steps {
        git 'https://github.com/xiaojin525/distroless-demo.git'
      }
    }
  }
  environment {
    label = 'pod-dind'
  }
}