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

	  }	
}
