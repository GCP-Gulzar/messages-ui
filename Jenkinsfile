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
                sh 'npm install -g node-gyp'
                sh 'docker run -ti google/cloud-sdk:latest'
            }
        }
    }
}
