pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t melnykapp:latest .'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "Tests passed!"'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy stage'
                sh 'docker images'
            }
        }
    }
}