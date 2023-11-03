pipeline {
    agent any
    stages {
        stage('Comprobar Compose') { 
            steps {
                sh '''
                    docker version
                    docker info
                    docker compose --version
                '''
            }
        }
        stage('Iniciar stack contenedores') {
            steps {
                sh '''
                    docker compose up -d --wait
                    docker compose ps
                '''
            }
        }
    }
    post {
        always {
            sh 'docker compose down'
            sh 'docker compose ps'
        }
    }
}