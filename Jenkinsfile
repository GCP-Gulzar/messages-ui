#!groovy​

pipeline {
  environment {
    version="00.00.01"
    tag="us.gcr.io/gcp-automated-networks-196019/message-ui:${version}"
  }
  agent {
      docker {
        image 'node'
        args '-u root:sudo'
      }
  }
  stages {
        stage('set env'){
          steps {
            deleteDir()
            docker.image('google/cloud-sdk').inside {

            }
          }
        }
        stage('build') {
            steps {
                deleteDir()
                sh 'npm --version'
                sh 'npm install -g node-gyp'
                sh 'ng build --prod'
            }
        }
    }
}
