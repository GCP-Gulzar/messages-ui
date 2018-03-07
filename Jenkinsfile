#!groovy​

pipeline {
    agent { docker 'node' }
    stages {
        stage('build') {
            steps {
                deleteDir()
                sh 'npm --version'
                sh "mkdir -p ~/.npm-global"
                sh "npm config set prefix '~/.npm-global'"
                sh "export PATH=~/.npm-global/bin:$PATH"
                sh "source ~/.profile"
                sh 'npm install -g @angular/cli'
                sh 'docker run -ti google/cloud-sdk:latest'
            }
        }
    }
}
