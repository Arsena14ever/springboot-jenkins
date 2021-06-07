pipeline {
  agent any
  stages {
    stage('package') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('product') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}