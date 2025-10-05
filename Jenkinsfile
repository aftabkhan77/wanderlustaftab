pipeline {
    agent any

    environment {
        PROJECT_NAME = "wanderlust_app"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/aftabkhan77/wanderlustaftab.git',
                    credentialsId: 'aftabkhan77'
            }
        }

        stage('Build & Deploy with Docker Compose') {
            steps {
                script {
                        sh 'sudo docker-compose -p ${PROJECT_NAME} down'
                        sh 'sudo docker-compose -p ${PROJECT_NAME} up -d --build'
                }
            }
        }
    }
}
