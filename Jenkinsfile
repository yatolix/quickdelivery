pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'scripts\\install_dependencies.bat'  // Use .bat or .ps1 files
            }
        }
        stage('Checkout') {
            steps {
                git 'https://github.com/yatolix/quickdelivery.git'
            }
        }
        stage('Build and Test') {
            steps {
                bat 'scripts\\build_and_test.bat' 
            }
        }
        stage('Deploy') {
            steps {
                bat 'scripts\\deploy.bat'
            }
        }
    }
}