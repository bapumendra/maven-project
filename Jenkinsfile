pipeline {
  agent any
    stages {
      stage ('Build') {
        steps {
          sh '/Users/SNIGDHA/downloads/apache-maven-3.5.2/bin/mvn clean'
        }
        post {
          success {
            echo 'Now Archiving . . .'
            archiveArtifacts artifacts: '**/*.war'
          }
        }    
      }
    }
}
