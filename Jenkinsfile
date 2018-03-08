node{
def version="00.00.01"
def tag="us.gcr.io/gcp-automated-networks-196019/message-ui:${version}"
def key=readFile("key.json")
def gcpProject="gcp-automated-networks-196019"

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
    }
    stage('deploy'){
    writeFile(file:"key.json",text:"$key")
    sh 'gcloud auth activate-service-account compute-engine-default@gcp-automated-networks-196019.iam.gserviceaccount.com --key-file=key.json'
    sh "gcloud config set project ${gcpProject}"
    sh "gcloud beta compute instance-groups managed rolling-action restart message-ui-instance-group2 \
       --region us-east1"
    }
}
