pipeline {
    agent any
        stages{
            stage('Build') {
                    steps{
                        sh'mvn clean package'
                    }
                    process {
                        success {
                            echo "Archeving Artifacts......"
                            archieveArticacts artifacts: '**/target/*.war'
                        }
                    }
            }
        }
}