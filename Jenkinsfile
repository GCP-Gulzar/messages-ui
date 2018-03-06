node{
def version="00.00.01"
def tag="us.gcr.io/gcp-automated-networks-196019/message-ui:${version}"

    stage('checkout'){
        echo 'Checking out source code...'
        checkout scm
    }
    stage('build'){
        echo "Building app..."
        echo "node version : "
        sh 'npm install'
        sh 'ng build --prod'
    }
    stage('dockerize'){
        echo 'dockerizing image...'
        sh "docker build -t ${tag} ."
        sh "curl https://sdk.cloud.google.com | bash"
        sh "gcloud docker --push ${tag}"
    }
}
