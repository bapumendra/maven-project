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
          archiveArtifacts artifacts: '**/*.war'
        }
      }    
    }
    stage ('Deploy to Staging') {
      steps {
        build job: 'second-deploy-to-staging'
      }
    }
    stage ('Deploy to Production') {
      steps {
        timeout (time:5, unit:'DAYS'){
          input message :'Approve Production Deployment'
        }
        build job : 'deploy-to-prod'
      }
      post {
        success {
          echo 'Code deployed to production'
        }
        failure {
          echo 'Deployment failed'
        }
      }
    }
  }
}
