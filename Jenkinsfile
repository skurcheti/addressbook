pipeline {
    agent any
	stages {
	  stage('Build'){
              steps{
              sh 'mvn clean compile'
               }
	    }
        stage('Archive-artifacts'){
             steps {
                archiveArtifacts artifacts: '**/target/*.war'
             }
         }
        }
}
   
