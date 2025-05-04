pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'wsl bash scripts/install_dependencies.sh'
            }
        }
        stage('Checkout') {
            steps {
                git 'https://github.com/yatolix/quickdelivery.git'
            }
        }
        stage('Build and Test') {
            steps {
                bat 'wsl bash scripts/build_and_test.sh' 
            }
        }
        stage('Deploy') {
            steps {
                bat 'wsl bash scripts/deploy.sh' 
            }
        }
    }
}