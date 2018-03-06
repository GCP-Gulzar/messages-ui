def version="00.00.01"
node{
def nodeHome = tool name: 'node-8.4.0', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
env.PATH = "${nodeHome}/bin:${env.PATH}"

    stage('checkout'){
        echo 'Checking out source code...'
        deleteDir()
        checkout scm
    }
    stage('build'){
        echo "Building app..."
        echo "node version : "
        sh "node -v"
        sh "npm install"
        sh "npm run-script build"
    }
    stage('dockerize'){
      
    }
}
