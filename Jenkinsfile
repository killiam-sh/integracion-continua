pipeline {
    agent any

    stages {
        stage('Clonar repositorio') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/killiam-sh/integracion-continua'
            }
        }

        stage('Verificar contenedores') {
            steps {
                sh 'docker ps'
            }
        }

        stage('Verificar conexión') {
            steps {
                sh 'sleep 5'
                sh 'curl -f http://flask_app:5000 || exit 1'
            }
        }
    }

    post {
        success {
            echo 'Pipeline ejecutado exitosamente'
        }
        failure {
            echo 'Pipeline falló'
        }
    }
}