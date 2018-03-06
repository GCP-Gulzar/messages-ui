def version="00.00.01"
pipeline{
  agent {
    docker {
         image 'node:6-alpine'
         args '-p 3000:3000'
     }
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
}
