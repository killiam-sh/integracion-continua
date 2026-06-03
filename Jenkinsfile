pipeline {
    agent any

    stages {
        stage('Clonar repositorio') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/killiam-sh/integracion-continua'
            }
        }

        stage('Construir imágenes') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Levantar contenedores') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('Verificar conexión') {
            steps {
                sh 'sleep 15'
                sh 'curl -f http://localhost:5000 || exit 1'
            }
        }

        stage('Bajar contenedores') {
            steps {
                sh 'docker compose down'
            }
        }
    }

    post {
        failure {
            sh 'docker compose down'
            echo 'Pipeline falló — contenedores detenidos'
        }
        success {
            echo 'Pipeline ejecutado exitosamente'
        }
    }
}