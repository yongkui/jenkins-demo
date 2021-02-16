pipeline{
  agent any
  
  stages{
    stage("run frontend") {
      echo 'executing yarn...'
      nodejs("Node1017") {
        sh 'yarn install'
      }
    }
    stage("run backend") {
      echo 'executing gradle...'
      withGradle() {
        sh './gradlew -v '
      }
      
    }
  
  }

}
