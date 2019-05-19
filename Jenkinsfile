pipeline {
  agent {
<<<<<<< HEAD
    label 'jenkinslave'
  }

  stages {
    stage('Fetch dependencies') {
      agent any
      steps {
        withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'venu-ocir-creds',
          usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
          sh 'echo uname=$USERNAME pwd=$PASSWORD'
      }
        sh 'whoami'
      }
    }
    stage('Build docker image') {
      agent any
      steps {
        sh 'sudo docker build . -t venuhello:1'
      }
    }
    stage('Test image') {
      agent any
      steps {
        sh 'echo "Tests successful"'
      }
    }
    stage('Push image to OCIR') {
      agent any
      steps {
          sh 'echo "Tests successful"'
        
      }
    }
  }

=======
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
>>>>>>> b1c77cc9912de66390573370bb01321e5e5c42db
