pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Stop Containers') {
            steps {
                sh 'docker-compose down || true'
            }
        }

        stage('Run Containers') {
            steps {
                sh 'docker-compose up -d --build'
            }
        }
    }
}
