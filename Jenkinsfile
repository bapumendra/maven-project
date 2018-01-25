pipeline {
  agent any
    stages {
      stage ('Build') {
        steps {
          sh '/Users/SNIGDHA/downloads/apache-maven-3.5.2 mvn clean package-pipeline'
        }
        post {
          success {
            echo 'Now Archiving . . .'
            archiveArtifacts artifacts: '**/target/*.war'
          }
        }    
      }
    }
}
