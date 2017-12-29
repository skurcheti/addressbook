


pipeline {
	agent any
	  stages{
	  	stage('Code Checking'){
	  		steps{
	  			echo "This Phase check code from the remote repo"
	  		}
	  	}
	  	stage('Testing the code'){
	  		steps{
	  			echo " Testing Code . . ."
	  			sh 'mvn test'
	  		}
	  	}
	  	stage('compiling stage'){
	  		steps{
	  			echo " This stage compile the code"
	  			sh 'mvn compile'
	  		}
	  	}

	  	stage('Packaging WAR'){
	  		steps{
	  			echo "WAR file is being created"
	  			sh 'mvn package'
	  		}
	  	} 
	  	stage('Archiving Artifacts'){
	  		steps{
	  			echo "This phase archive artifacts"
	  			archiveArtifacts artifacts: '**/target/*.war'
	  		}
	  	}
	 } 
}
