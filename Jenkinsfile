pipeline {
  agent {
    node {
      label 'any'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        echo 'todo build'
        withMaven(maven: 'M35') {
          sh 'mvn clean install'
        }
        
        checkstyle(pattern: 'target/checkstyle-result.xml')
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