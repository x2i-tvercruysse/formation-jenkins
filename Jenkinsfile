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
          sh "mvn clean install"
        }
        checkstyle canComputeNew: false, defaultEncoding: '', healthy: '', pattern: 'target/checkstyle-result.xml', unHealthy: ''
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
