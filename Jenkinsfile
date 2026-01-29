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
        archiveArtifacts '**/target/*.jar'
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