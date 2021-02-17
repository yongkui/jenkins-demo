pipeline{
  agent any
  
  stages {
  
    stage("build") {
      steps {
         echo "building application..."
         echo "application built."
      }
    }
  
    stage("test") {
      steps {
         echo "testing application..."
      }
    }
  
   stage("deploy") {
      steps {
         echo "deploying application..."
      }
    }

  }
  
  post {
    always{
      echo "here is something that will always be done."
    }
    
    success{
      echo "here is something that will be done when build is successful."
    }
    
    failure{
      echo "here is something that will be done when build is failed."
    }
    
  }

}
