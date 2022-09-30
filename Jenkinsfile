pipeline {
  agent { label 'docker-agent-alpine' }
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('shubhamspy-dockerhub')
  }
  stages {
    stage('Build') {
      steps {
        sh './jenkins-learning/build.sh'
      }
    }
    stage('Login') {
      steps {
        sh './jenkins-learning/login.sh'
      }
    }
    stage('Push') {
      steps {
        sh './jenkins-learning/push.sh'
      }
    }
  }
  post {
    always {
      sh './jenkins-learning/logout.sh'
    }
  }
}