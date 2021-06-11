pipeline {
  agent any
  tools {
     maven "mvn_381"
  }
  stages {
    stage('MVN Build') {
      post {
        success {
          echo 'Only when we haven\'t failed running the first stage'
        }

        failure {
          echo 'Only when we fail running the first stage.'
        }

      }
      steps {
        sh "mvn clean install"
      }
    }

    stage('checkstyle') {
      steps {
        sh "mvn checkstyle:checkstyle"
        recordIssues(tools: [checkStyle(pattern: 'target/checkstyle-result.xml')])
        recordIssues(tools: [java()])
        recordIssues(tools: [taskScanner(highTags: '//TODO', includePattern: '**/*.java', normalTags: '//ORSYS-FIXME')])
      }
    }
    
    stage('Junit') {
      steps {
        recordIssues(tools: [junitParser(pattern: 'target/surefire-reports/TEST-*.xml')])
      }
    }

    stage('SONAR & Jmeter') {
      steps {
         sh "mvn spring-boot:start jmeter:jmeter spring-boot:stop"
      }
    }

  }
  environment {
    FOO = 'BAR'
  }
}
