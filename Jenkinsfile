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
        sh 'id'
      }
    }
  }
}
