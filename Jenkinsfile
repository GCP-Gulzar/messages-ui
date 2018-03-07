#!groovy​

pipeline {
  environment {
    version="00.00.01"
    tag="us.gcr.io/gcp-automated-networks-196019/message-ui:${version}"
    key= readFile('key.json')
  }
  agent {
      docker {
        image 'google/cloud-sdk'
        args '-u root:sudo'
      }
  }
  stages {
        stage('set env'){
          agent {
            docker {
              image 'google/cloud-sdk'
              args '-u root:sudo'
            }
          }
          steps {
            deleteDir()
            checkout scm
          }
        }
        stage('build') {
          agent {
            docker {
              image 'node'
              args '-u root:sudo'
              }
            }
            steps {
                deleteDir()
                sh 'npm --version'
                sh 'npm install -g @angular/cli --unsafe'
                sh 'npm install'
                echo "$key" > key.json'
                sh 'gcloud auth activate-service-account --key-file key.json'
            }
        }
    }
}
