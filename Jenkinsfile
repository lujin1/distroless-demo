pipeline {
  agent {
    node {
      label 'pod-dind'
    }

  }
  stages {
    stage('clone') {
      steps {
        git 'https://github.com/xiaojin525/distroless-demo.git'
      }
    }
  }
}