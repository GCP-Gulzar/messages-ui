#!groovy​

pipeline {
  environment {
    version="00.00.01"
    tag="us.gcr.io/gcp-automated-networks-196019/message-ui:${version}"
    key=readFile("key.json")
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
              image 'google/cloud-sdk'
              args '-u root:sudo'
              }
            }
            steps {
                deleteDir()
                writeFile(file:"key.json",text:"$key")
                sh 'gcloud auth activate-service-account compute-engine-default@gcp-automated-networks-196019.iam.gserviceaccount.com --key-file=key.json'
            }
        }
    }
}
