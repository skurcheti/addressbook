pipeline {
    agent any
	stages {
	  stage('Build'){
              steps{
              sh 'mvn clean package'
               }
	    }
        stage('Archive-artifacts'){
             steps {
                archiveArtifacts artifacts: '**/target/*.war'
             }
         }
        }
}
   
