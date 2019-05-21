pipeline {
  agent {
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
        sh 'docker build . -t venuhello:1'
        sh 'whoami'
        withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'venu-ocir-creds',
          usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
          sh 'sudo docker login -u $USERNAME -p $PASSWORD phx.ocir.io'
        }  
        sh'docker tag venuhello:1 phx.ocir.io/ociateam/venuhello:1'
        sh 'docker push phx.ocir.io/ociateam/venuhello:1'
        sh 'echo "Tests successful"'
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
          
          sh 'whoami'
        
      }
    }
  }
}
