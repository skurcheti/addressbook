pipeline {
   agent any 
      stages{
	   stage('Cleaning the target folder'){
               steps {
                   sh 'mvn clean'
               }
            }
           stage('testing the repository'){
                   sh 'mvn test'
           }     
           stage('Compiling the code'){
                  sh 'mvn compile'
           }
	   stage('packaging the code'){
                  sh 'mvn package'
           }

      }

}















