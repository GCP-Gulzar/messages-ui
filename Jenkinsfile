#!groovy​

pipeline {
    agent { docker 'node' }
    stages {
        stage('build') {
            steps {
                deleteDir()
                sh 'npm --version'
                docker.image('openjdk:8').inside {
                  withEnv
                }
                sh 'npm install -g @angular/cli'
                sh 'docker run -ti google/cloud-sdk:latest'
            }
        }
    }
}
