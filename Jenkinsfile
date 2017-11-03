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
            stage ('Deploy to sgarnng'){
                steps {
                    build job:'pipe-deploy-stag'
            }
                }
        }
}