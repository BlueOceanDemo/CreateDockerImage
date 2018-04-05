pipeline {
  agent {
    node {
      label 'docker'
    }
    
  }
  stages {
    stage('BuildImage') {
      steps {
        sh 'docker build -t test/image:0.1 .'
      }
    }
  }
}