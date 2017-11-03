pipeline {
    agent any
        stages {
            stage('Build'){
                steps {
                    sh 'mvn clean package'
                }
                post{
                        success {
                            echo "Archiving Artifacts .. . . . . ..."
                            archiveArtifacts artifacts:'**/target/*.war'
                        }
                }
            }
            stage ('Deploy to stagning'){
                steps {
                    build job:'pipe-deploy-stag'
            }
                }
            stage ('Deploy to production'){
                steps {
                    build job:'pipe-deploy-prod'
            
                }    }
        }
}


