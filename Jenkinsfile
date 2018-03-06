node{
def version="00.00.01"
    stage('checkout'){
        echo 'Checking out source code...'
        checkout scm
    }
    stage('build'){
        echo "Building app..."
        echo "node version : "
        sh 'npm install'
        sh 'ng build'
    }
    stage('dockerize'){
        echo 'dockerizing image...'
        sh 'docker -t message-ui:${version} .'
    }
}
