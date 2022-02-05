pipeline {
  agent any
  environment {
    MESSAGE = "Hello Jenkins!"
  }
  stages {
    stage('say hello') {
      steps {
        echo $MESSAGE
      }
    }
    stage('main') {
      when { branch 'main' }
      steps {
        echo 'MAIN'
      }
    }
    stage('develop') {
      when { branch 'develop' }
      steps {
        echo 'DEVELOP'
      }
    }
  }
  post {
    cleanup {
      cleanWs()
    }
  }
}