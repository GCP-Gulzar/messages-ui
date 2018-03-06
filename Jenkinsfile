def version="00.00.01"
def nodeHome = tool "node-8.4.0"
env.PATH = "${nodeHome}/bin:${env.PATH}"

node {
  stage('checkout'){
    echo 'Checking out source code...'
    deleteDir()
    checkout scm
  }

  stage('build'){
    echo 'Building app...'
    echo 'node version : '
    sh "node -v"
    sh "ng build --prod"
  }
}
