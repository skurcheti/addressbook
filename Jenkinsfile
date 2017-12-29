

pipeline {
	agent any 
	   triggers {
	   	pollSCM('* * * * *')
	   }
	   stages{
	   	 stage('Packaging in war'){
	   	 	 steps{
	   	 	 	sh 'mvn package'
	   	 	 }
	   	 }

	   	 stage('Archive Artifacts'){
	   	 	steps{
	   	 		archiveArtifacts artifacts: '**/target/*.war'
	   	 	}
	   	 }
	   	 stage('Deployment'){
	   	 	steps{
	   	 		sh "cp target/addressbook-2.0.war /var/lib/tomcat/webapps/addressbook-2.0.war'
	   	 	}
	   	 }
	   }
}
