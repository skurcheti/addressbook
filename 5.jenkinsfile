
pipeline {
  agent any
      stages {
          stage('Maven Clean and Compile'){
              steps{
		sh 'mvn clean compile'
                }
          }
       stage('testing'){
          steps{
                 sh 'mvn test'
             }
       }
       stage('package'){
           steps{
              sh 'mvn package'
              }
       }
      stage('Archive Artifacts'){
          steps {
               
                   archiveArtifacts artifacts:'**/target/*.war'  
               }
         }
  }
}
