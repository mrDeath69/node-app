pipeline {
  agent any

  stages {
    stage ('Clone') {
      steps {
        git https://github.com/mrDeath69/node-app.git
      }
    }
    stage ('Build') {
      steps {
        sh 'docker build -t node-app .'
      }
    }
    stage ('Deploy') {
      steps {
        sh 'docker run -d -p 3000:3000 --name node-app'
      }
    }
  }

  post {
    always {
      sh 'docker ps -a'
    }
  }
}
