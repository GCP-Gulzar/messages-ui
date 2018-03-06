def version="00.00.01"

node {

    def build(){
      checkout()
      compile()
      dockerize()
      test()
      deploy()
    }

    def checkout(){
      stage('checkout'){
      deleteDir()
      checkout scm
      }
    }

    def dockerize(){

    }


}
