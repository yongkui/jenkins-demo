pipeline{
  agent any
  
  tools {
    gradle 'Gradle-6.8.2'
  }
  
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
         echo "deploying application...'
         sh './gradlew -v'
      }
    }

  }

}
