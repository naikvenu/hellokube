pipeline {
  agent {
    docker {
      image 'nginx:latest'
    }

  }
  stages {
    stage('Stage') {
      steps {
        sh 'whoami'
      }
    }
  }
}