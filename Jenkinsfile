pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000 -u root'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'npm install'
      }
    }
    stage('test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
        input 'proceed to continue'
        sh './jenkins/scripts/kill.sh'
      }
    }
  }
}