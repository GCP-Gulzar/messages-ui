def version="00.00.01"
env.PATH = "${nodeHome}/bin:${env.PATH}"

node {
  agent {
       docker { image 'node:7-alpine' }
   }
  stage('checkout'){
    echo 'Checking out source code...'
    deleteDir()
    checkout scm
  }

  stage('build'){
    echo "Building app..."
    echo "node version : "
    sh "node -v"
    sh "ng build --prod"
  }
}
