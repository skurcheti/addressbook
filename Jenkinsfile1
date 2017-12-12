pipeline {
	agent any
	stages{
		stage('Init'){
			steps {
				echo "This is Init Stage"

		      	}		
		}

		stage('check-code'){
			steps {
				echo "This is checking your code"

               		}

		}
		stage('Compiling-war-file'){

			steps{
				echo "Compiling war files . . ."
			}
		}

		stage('Archieving-Artifacts'){
			steps{
				echo " Archeving Artifacts . . "
			}
		
		}

		stage('Deploying-Artifacts'){
			steps {
				echo "This stage Deploy war file to Tomcat"
				echo "TOMCAT is absent so ending the process"
			}
		}

	}
}  















