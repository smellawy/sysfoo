pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package -DskipTests'
        archiveArtifacts(artifacts: '**/target/*.jar', allowEmptyArchive: true)
      }
    }

    stage('Debug') {
      steps {
        sh '''
                pwd
                ls -R
                '''
      }
    }

  }
  tools {
    maven 'Maven'
  }
}