def version="00.00.01"
pipeline{
  agent any
  stages{
    stage('checkout'){
      steps{
        echo 'Checking out source code...'
        deleteDir()
        checkout scm
      }
    }
    stage('build'){
      steps{
        echo "Building app..."
        echo "node version : "
        sh "node -v"
        sh "ng build --prod"
        docker.build('')
      }
    }
  }
}
