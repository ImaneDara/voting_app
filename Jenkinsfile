pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/ImaneDara/voting_app.git'
      }
    }

    stage('Stop Old Containers') {
      steps {
        sh 'docker compose down --remove-orphans || true'
      }
    }

    stage('Build Images') {
      steps {
        sh 'docker compose build'
      }
    }

    stage('Run Containers') {
      steps {
        sh 'docker compose up -d'
      }
    }

    stage('Health Check') {
      steps {
        sh 'docker ps'
      }
    }
  }

  post {
    success {
      echo 'Déploiement réussi !'
    }
    failure {
      echo 'Échec du pipeline.'
    }
  }
}

