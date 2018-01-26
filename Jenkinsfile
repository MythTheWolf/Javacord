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
    stage('Document') {
      sh 'mvn javadoc:javadoc'
      publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'target/site/apidocs', reportFiles: 'index.html', reportName: 'Docs', reportTitles: 'index'])
    }
  }
}
