def version="00.00.01"
def nodeHome = tool name: 'node-8.4.0', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
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
    docker.image('node:4.1.2').inside {
      sh 'node -v'
      sh 'ng build --prod'
    }
  }
}
