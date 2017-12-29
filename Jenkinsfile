pipeline {
   agent any 
          stages {
	  stage('Build'){
              steps{
              sh 'mvn clean package'
               }
	    }

           stage('testing the repository'){
              steps {    
                sh 'mvn test'
           }   }  
           stage('Compiling the code'){
                steps {
		  sh 'mvn compile'
           }}
	   stage('packaging the code'){
                steps { 
                 sh 'mvn package'
           }}

      }

}















