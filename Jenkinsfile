
pipeline {
  agent any
      stages {
          stage(Maven Clean and Compile){
              steps{
                withMaven(maven: 'mvn') {
		sh 'mvn clean compile'
                }
              }
          }
       stage('testing'){
          steps{
             withMaven(maven: 'mvn'){
                 sh 'mvn test'
             }
           }
       }
       stage('package'){
           steps{
              withMaven(maven: 'mvn){
              sh 'mvn package'
              }
           }
       }
      stage('Deploy to local repo'){
         steps {
           withMaven('maven: mvn'){
              steps {
                sh 'mvn deploy'
              }
           }
         }
      }
      stage('Archive Artifacts'){
         withMaven(maven: 'mvn'){
               steps {
                   archiveArtifacts artifacts: '**/target/*.war'  
               }
         }
    
    }
}
