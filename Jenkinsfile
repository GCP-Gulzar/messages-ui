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
        sh "npm run-script build"
    }
}
