pipeline {
    agent any
        stages {
            stage('Build'){
                steps {
                    sh'mvn clean package'
                }
                process {
                        success {
                            echo "Archiving Artifacts .. . . . . ..."
                            archiveArtifacts artifacts:'**/target/*.war'
                        }
                }
            }
        }
}