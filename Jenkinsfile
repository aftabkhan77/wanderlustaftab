pipeline {
    agent any

    environment {
        PROJECT_NAME = "wanderlust_app"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aftabkhan77/wanderlustaftab.git',
                    credentialsId: 'e342e387-f202-4349-979a-32f5d0f36d5a'
            }
        }

        stage('Build & Deploy with Docker Compose') {
            steps {
                script {
                        sh 'docker-compose -p ${PROJECT_NAME} down'
                        sh 'docker-compose -p ${PROJECT_NAME} up -d --build'
                }
            }
        }
    }
}
