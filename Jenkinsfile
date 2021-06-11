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
        echo 'This time, the Maven version should be 3.5.3'
      }
    }

    stage('SONAR & Jmeter') {
      parallel {
        stage('one') {
          steps {
            echo 'I\'m on the first branch!'
          }
        }

        stage('two') {
          steps {
            echo 'I\'m on the second branch!'
          }
        }

        stage('three') {
          steps {
            echo 'I\'m on the third branch!'
            echo 'But you probably guessed that already.'
          }
        }

      }
    }

  }
  environment {
    FOO = 'BAR'
  }
}
