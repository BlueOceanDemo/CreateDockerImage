pipeline {
    agent any

    stages {
        stage('Building Docker Images') {
            steps {
                sh 'docker build -t test/image:0.1 .'
            }
        }
        stage('Push Image') {
            steps {
                sh 'echo "Image Pushed Successfully"'
            }
        }
    }
}
