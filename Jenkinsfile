pipeline {
  agent any
  tools {
    maven 'localMaven'
  }
  stages {
    stage ('Build') {
      steps {
        sh '/Users/SNIGDHA/downloads/apache-maven-3.5.2/bin/mvn clean package'
      }
      post {
        success {
          echo 'Now Archiving . . .'
          archiveArtifacts artifacts: '**/*'
        }
      }    
    }
  }
}
