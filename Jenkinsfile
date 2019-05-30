pipeline {
  agent {
    node {
      label 'pod-dind'
    }

  }
  stages {
    stage('clone') {
      steps {
        container('pod-dind'){
        git 'https://github.com/xiaojin525/distroless-demo.git'
        }
      }
    }
    stage('DockerBuild') {
      steps {
        container('pod-dind'){
        sh 'docker build -t harbor.eastasia.cloudapp.azure.com/lujin/distroless-demo:v1 .'
        }
      }
    }
    stage('DockerLogin') {
      steps {
        container('pod-dind'){
        sh 'docker login harbor.eastasia.cloudapp.azure.com -u lu.jin@advantech.com.cn -p 1qazXSW@'
        }
      }
    }
    stage('DockerPush') {
      steps {
        container('pod-dind'){
        sh 'docker push harbor.eastasia.cloudapp.azure.com/distroless-demo:v1'
        }
      }
    }
  }
}
