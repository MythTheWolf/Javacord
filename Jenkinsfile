pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build 'Javacord'
      }
    }
    stage('Release') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }
  }
}