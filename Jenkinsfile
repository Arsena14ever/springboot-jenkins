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
        archiveArtifacts 'demo/target/*.jar'
      }
    }

    stage('scp') {
      steps {
        sh 'scp -r /var/jenkins_home/workspace/springboot-jenkins_master/demo/target/demo-1.0-SNAPSHOT.jar root@106.14.37.126:/home/springboot-jenkins/'
      }
    }

    stage('run') {
      steps {
        sh '''ssh root@106.14.37.126 "nohup java -jar /home/springboot-jenkins/demo-1.0-SNAPSHOT.jar &"
'''
      }
    }

  }
}