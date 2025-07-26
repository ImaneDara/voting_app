pipeline {
    agent any

    stages {
        stage('Cloner le projet') {
            steps {
                git 'https://github.com/ImaneDara/voting_app.git'
            }
        }

        stage('Build des images') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Déploiement') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }
}

