pipeline {
  agent {
    node {
      label 'slave1'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        echo 'todo build'
        withMaven(maven: 'M35') {
          mvn install
      }

      }
    }
    stage('Test') {
      steps {
        echo 'todo test'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy'
      }
    }
  }
}
