#!groovy​

pipeline {
    agent { docker 'node' }
    stages {
        stage('build') {
            steps {
                deleteDir()
                sh 'npm --version'
                sh 'npm install -g @angular/cli'
                sh 'docker run -ti google/cloud-sdk:latest'
            }
        }
    }
}
