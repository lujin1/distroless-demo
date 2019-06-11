pipeline {
  agent { label 'docker-dind' }
  stages {
    stage('clone') {
      steps {
        container('docker-dind'){
        sh "whoami"
        sh "docker ps" 
        git 'https://github.com/xiaojin525/distroless-demo.git'
        }
      }
    }
    stage('DockerBuild') {
      steps {
        container('docker-dind'){
        sh 'docker build -t harbor.com/lujin/distroless-demo:v1 .'
        }
      }
    }
    stage('DockerLogin') {
      steps {
        container('docker-dind'){
        sh 'docker login harbor.com -u lu.jin@advantech.com.cn -p @PASSWORD'
        }
      }
    }
    stage('DockerPush') {
      steps {
        container('docker-dind'){
        sh 'docker push harbor.com/lujin/distroless-demo:v1'
        }
      }
    }
  }
}
