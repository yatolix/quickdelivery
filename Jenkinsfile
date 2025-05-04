pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'sh scripts/install_dependencies.sh'
            }
        }
        stage('Checkout') {
            steps {
                git 'https://github.com/yatolix/quickdelivery.git'
            }
        }
        stage('Build and Test') {
            steps {
                sh 'sh scripts/build_and_test.sh'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sh scripts/deploy.sh'
            }
        }
    }
}