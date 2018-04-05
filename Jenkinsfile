pipeline {
  agent {
    node {
      label 'master'
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