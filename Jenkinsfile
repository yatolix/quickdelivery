pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat '''
                    docker run --rm -v "%cd%:/app" ubuntu:latest /bin/bash -c "
                        apt-get update -qq &&
                        apt-get install -y dos2unix > /dev/null &&
                        cd /app &&
                        dos2unix scripts/install_dependencies.sh &&
                        chmod +x scripts/install_dependencies.sh &&
                        ./scripts/install_dependencies.sh
                    "
                '''
            }
        }
        stage('Checkout') {
            steps {
                git 'https://github.com/yatolix/quickdelivery.git'
            }
        }
        stage('Build and Test') {
            steps {
                bat '''
                    docker run --rm -v "%cd%:/app" ubuntu:latest /bin/bash -c "
                    apt-get update -qq &&
                    apt-get install -y dos2unix > /dev/null &&
                    cd /app &&
                    dos2unix scripts/build_and_test.sh &&
                    chmod +x scripts/build_and_test.sh &&
                    ./scripts/build_and_test.sh
                    "
                '''
            }
        }
        stage('Deploy') {
            steps {
                bat '''
                    docker run --rm -v "%cd%:/app" ubuntu:latest /bin/bash -c "
                    apt-get update -qq &&
                    apt-get install -y dos2unix > /dev/null &&
                    cd /app &&
                    dos2unix scripts/deploy.sh &&
                    chmod +x scripts/deploy.sh &&
                    ./scripts/deploy.sh
                    "
                '''
            }
        }
    }
}