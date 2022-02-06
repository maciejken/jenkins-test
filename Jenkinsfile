pipeline {
  agent any
  parameters {
    string(name: "YOUR_NAME", defaultValue: "Jenkins")
  }
  environment {
    MESSAGE = "Hello ${params.YOUR_NAME}!"
  }
  stages {
    stage('say hello') {
      steps {
        echo "${MESSAGE}"
        echo "${env.BRANCH_NAME}"
      }
    }
    stage('main') {
      when { branch 'main' }
      steps {
        echo 'MAIN'
        echo 'here is the place for the main docker-compose.yml'
      }
    }
    stage('develop') {
      when { branch 'develop' }
      steps {
        echo 'DEVELOP'
        echo 'here we can use an alternative docker-compose config just for testing'
      }
    }
  }
  post {
    cleanup {
      cleanWs()
    }
  }
}