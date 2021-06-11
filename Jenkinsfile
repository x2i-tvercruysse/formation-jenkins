pipeline {
  agent any
  stages {
    stage('first stage') {
      post {
        success {
          echo 'Only when we haven\'t failed running the first stage'
        }

        failure {
          echo 'Only when we fail running the first stage.'
        }

      }
      steps {
        timeout(time: 10, unit: 'MINUTES') {
          echo 'We\'re not doing anything particularly special here.'
          echo 'Just making sure that we don\'t take longer than five minutes'
          echo 'Which, I guess, is kind of silly.'
        }

      }
    }

    stage('second stage') {
      steps {
        echo 'This time, the Maven version should be 3.5.3'
      }
    }

    stage('third stage') {
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