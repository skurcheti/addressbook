
pipeline {
        agent any
        stages{
                stage('Build'){
                        steps {
                                sh 'mvn clean package'
                        }
			post {
			   success {
				echo "Now archeving"
				archiveArtifacts artifacts: '**/target/*.war'
			   }
			}
			
                 }
		 stage('Deploy to Stagning'){
                    steps { 
                        build job: 'Deploy-to-stagning'
                     
		    }
		}
                stage('Deploy to Production'){
                   steps{
                       timeout(time:5, unit:'DAYS'){
		             input message: 'Approve PRODUCTION Deployment?'
		       }
		        build job: 'Deploy-to-prod'
                }
 		post {
		   success {
			echo 'Code Deployment to Production'
                   }
		   failure {
                     echo 'Deployment Failed'
                   }
     	        }	
                }  
        }
}
