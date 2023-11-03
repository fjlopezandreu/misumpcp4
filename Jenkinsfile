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
                    docker compose up -d
                    docker compose ps
                '''
            }
        }
    }
}