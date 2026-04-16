pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/CloudWithShan/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Run Containers') {
            steps {
                sh 'docker-compose down || true'
                sh 'docker-compose up -d'
            }
        }
    }
}
