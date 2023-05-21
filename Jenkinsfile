pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('docker')
  }
  stages {
    stage('Build') {
      steps {
        // sh 'docker build -t neilthegreat07/jenkins-docker-hub:nginx-devops-v-$BUILD_NUMBER .'
        sh "echo 'this is build phase'"
      }
    }
    stage('Login') {
        steps {
            // sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            sh "echo 'this is login phase'"
        }
    }
    stage('Push') {
      steps {
        // sh 'docker push neilthegreat07/jenkins-docker-hub:nginx-devops-v-$BUILD_NUMBER'
        sh "echo 'this is push phase'"
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}

