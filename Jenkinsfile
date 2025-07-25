pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
            }
        }

        stage('Build Docker Images') {
            steps {
                script {
                    sh 'docker-compose -f deploy/docker-compose/docker-compose.yaml build'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'docker-compose -f deploy/docker-compose/docker-compose.yaml up -d'
                }
            }
        }
    }
}
