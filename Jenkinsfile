pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'cd backend && docker build -t backend .'
                sh 'cd frontend && docker build -t frontend .'
            }
        }

        stage('Run') {
            steps {
                sh 'docker run -d -p 3001:3001 backend'
                sh 'docker run -d -p 3000:3000 frontend'
            }
        }
    }
}
