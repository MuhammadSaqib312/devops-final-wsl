pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/MuhammadSaqib312/devops-final-wsl'
            }
        }
        stage('Build Image') {
            steps {
                sh 'docker build -t laravel-app .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker stop laravel-app || true'
                sh 'docker rm laravel-app || true'
                sh 'docker run -d -p 8000:8000 --name laravel-app laravel-app'
            }
        }
    }
}
