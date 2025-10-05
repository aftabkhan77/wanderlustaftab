pipeline {
    agent any

    environment {
        PROJECT_NAME = "wanderlust_app"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aftabkhan77/wanderlustaftab.git'
            }
        }

        stage('Build & Deploy with Docker Compose') {
            steps {
                script {
                    sh """
                        docker compose -p ${PROJECT_NAME} down
                        docker compose -p ${PROJECT_NAME} up -d --build
                    """
                }
            }
        }
    }
}
