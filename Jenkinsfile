// CODE_CHANGES = getGitChanges()  // this does not work with error message: java.lang.NoSuchMethodError: No such DSL method 'getGitChanges' found among steps

pipeline{
  
  agent any
  
  environment {
    VERSION = '1.3.0' 
    SERVER_CREDENTIALS = credentials('server-credentials')
  }
  
  
  stages {
  
    stage("build") {
      
      when {
        expression{
            // BRANCH_NAME == 'file' && CODE_CHANGES == ‘true’
            BRANCH_NAME == 'file'
        }
      }
      
      steps {
         echo "building application..."
         echo "building version ${VERSION}"
      }
    }
  
    stage("test") {
      
      when {
        expression{
            BRANCH_NAME == 'dev'
        }
      }
      
      steps {
         echo "testing application..."
      }
    }
  
   stage("deploy") {
      steps {
         echo "deploying application..."
         echo "deploying with ${SERVER_CREDENTIALS}"
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
