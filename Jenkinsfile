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
        tool(name: 'M35', type: 'maven')
        sh 'mvn install'
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