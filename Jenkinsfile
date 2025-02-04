pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'your-docker-image-name'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git 'https://github.com/your-username/simple-repo.git'
            }
        }
        
        stage('Build with Maven') {
            steps {
                // Run Maven build
                script {
                    sh 'mvn clean install'
                }
            }
        }
        
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                script {
                    sh 'docker build -t $DOCKER_IMAGE .'
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                // Push Docker image to DockerHub or other registry
                script {
                    sh 'docker push $DOCKER_IMAGE'
                }
            }
        }
    }
}
