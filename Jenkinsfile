pipeline {
    agent any
	tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mymaven3.9.6"
    }
      stages{
         stage('checking Code'){
             steps {
               echo " This Stage Check Code in the remote repository"
               sleep 2
	     }
         }
          stage('Cleaning the target Folder'){
             steps{
                 echo " This stage is concerned in cleaning the target folder"
                 sh 'mvn clean'
             }
           }
	  stage('Compiling code'){
             steps{
                 echo " This stage is concerned with code compilation"
                 sh 'mvn compile'
             }
           }
          stage('testing the code'){
            steps {
  		echo "This stage is concerned on code analysis"
		sh 'mvn test'
            }
          }
          stage('Packaging of code'){
             steps { 
               echo " This stage makes the war file"
               sleep 5
               sh 'mvn package'
             }
          }
          stage('Archive Artifacts'){
            steps {
              echo "Archeving Artifacts . . . "
              archiveArtifacts artifacts: '**/target/*.war'
              echo "Well Done - Finished Archeving "
              sleep 5
            }
          }        
           stage('Deploying'){
             steps{
               echo "This process deploy the code in local Repository"
               sh 'mvn install'
               sleep 2
             }
          }
      }
}
