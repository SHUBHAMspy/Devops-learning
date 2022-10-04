pipeline {
  agent {
        docker {
            image 'node:16.17.0'
        }
    }
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('shubhamspy-dockerhub')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t shubhamspy/node-app-image .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push shubhamspy/node-app-image'
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}
