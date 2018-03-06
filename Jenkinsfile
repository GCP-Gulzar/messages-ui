def version="00.00.01"
node{
    stage('checkout'){
        echo 'Checking out source code...'
        deleteDir()
        checkout scm
    }
    stage('build'){
        echo "Building app..."
        echo "node version : "
        docker.image('node:4.1.2').inside {
        sh "node -v"
        sh "npm install -g @angular/cli"
        sh "npm run-script build"
        }
    }
}
