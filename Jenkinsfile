pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'docker run --rm -v "%cd%:/app" ubuntu:latest /bin/bash -c "cd /app && ./scripts/install_dependencies.sh"'
            }
        }
        stage('Checkout') {
            steps {
                git 'https://github.com/yatolix/quickdelivery.git'
            }
        }
        stage('Build and Test') {
            steps {
                bat 'docker run --rm -v "%cd%:/app" ubuntu:latest /bin/bash -c "cd /app && ./scripts/build_and_test.sh"'
            }
        }
        stage('Deploy') {
            steps {
                bat 'docker run --rm -v "%cd%:/app" ubuntu:latest /bin/bash -c "cd /app && ./scripts/deploy.sh"' 
            }
        }
    }
}