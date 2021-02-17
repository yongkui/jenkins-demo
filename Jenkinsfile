// CODE_CHANGES = getGitChanges()  // this does not work with error message: java.lang.NoSuchMethodError: No such DSL method 'getGitChanges' found among steps

pipeline{
  
  agent any
  
  environment {
    VERSION = '1.3.0' 
    SERVER_CREDENTIALS = credentials('server-credentials')
  }

  parameters {
    
    choice(name: 'Version', choices['1.1.0','1.2.0','1.3.0'], description: 'Please choose the version')
    booleanParam(name: 'executeTests', defaultValue: true, description: '')
    
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
       //  echo "building version ${VERSION}"
      }
    }
  
    stage("test") {
      
      when {
        expression{
          //  BRANCH_NAME == 'dev'
          params.executeTests == true
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
        echo "deploying version ${params.Version}"
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
