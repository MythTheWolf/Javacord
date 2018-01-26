pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        catchError() {
          sh 'mvn clean install'
        }
        
      }
    }
    stage('Release') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }
  }
}