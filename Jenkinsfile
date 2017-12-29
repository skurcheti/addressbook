

pipeline {
	agent any
	   parameters{
	   	string(name: 'tomcat_dev', defaultValue:'192.168.88.4', description:'Stagning Server')
	   	string(name: 'tomcat_prod', defaultValue:'192.168.88.4', description:'Production Server')
	   }
	   
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
	   	 		sh 'scp **/target/*.war root@${params.tomcat_dev}:/var/lib/tomcat/webapps'
	   	 	}
	   	 }
	   }
}
