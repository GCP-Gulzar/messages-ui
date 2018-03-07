#!groovy​

pipeline {
    agent {
      docker {
        image 'node'
        args '-u root:sudo'
      }
    }
    stages {
        stage('build') {
            steps {
                deleteDir()
                sh 'npm --version'
                sh "mkdir -p ~/.npm-global"
                sh "npm config set prefix '~/.npm-global'"
                sh "export PATH=~/.npm-global/bin:$PATH"
                sh 'npm install -g @angular/cli'
                sh 'docker run -ti google/cloud-sdk:latest'
            }
        }
    }
}
