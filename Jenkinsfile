pipeline {
  agent { 
    node { 
        label 'docker' 
    }
  }

parameters {
        string(name: 'Image_Version', defaultValue: '0.1', description: 'Enter The Image Version to build')
        choice(name: 'choice', choices: 'one\ntwo\nthree', description: 'Just testing it!')
        
    }

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
                sh "dpkg -l | grep docker"
            }
        }
        stage("Build") {
            steps {
                sh "pwd"
                sh "ls -ltrha"
                sh "docker build -t test/test:${params.Image_Version} ."
                sh "docker images ls | grep test/test"
            }
        }
        stage("Push") {
            when {
                branch 'master'
            }
            steps {
                sh "echo 'Pushed Image Successfully'"
            }
        }
    }
}
