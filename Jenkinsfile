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
    stage('DockerBuild') {
      steps {
        sh 'ls -l'
        sh 'pwd'
      }
    }
  }
}