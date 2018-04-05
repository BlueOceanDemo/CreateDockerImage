pipeline {
    agent any
    stages {
        stage("Checkout Code") {
            steps {
                script {
                    checkout scm
                }
            }
        }
        stage("Install Docker") {
            steps {
                sh "yum install docker -y"
            }
        }
        stage("Build") {
            steps {
                sh "pwd"
                sh "ls -ltrha"
                sh "docker build -t test/test:latest ."
            }
        }
        stage("Push") {
            when {
                branch 'master'
            }
            steps {
                sh "echo "Pushed Image Successfully""
            }
        }
    }
}
