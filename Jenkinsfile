pipeline {
  agent any
  stages {
    stage('Build and Test') {
      steps {
        sh 'docker-compose build --no-cache'
      }
    }
    if(env.BRANCH_NAME == 'dockerize'){
        stage('Deploy'){
            environment {
              WEBHOOKS_FILE = credentials('9adeeae1-50f8-4f8c-afac-b18df7d8b031')
            }
            steps {
              sh 'docker-compose down'
              sh 'docker-compose up -d'
            }

        }
    }
  }
}