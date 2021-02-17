pipeline{
  agent any
  
  stages {
  
    stage("front-end") {
      steps {
         echo "executing yarn..."
        nodejs("Node-10.17"){
            sh 'yarn install'
        }
      }
    }
  
   stage("back-end") {
      steps {
         echo "deploying application..."
        withGradle(){
            sh './gradlew -v'
        }
      }
    }

  }

}
