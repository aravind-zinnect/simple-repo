pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/aravind-zinnect/simple-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build commands here (e.g., Maven or npm)
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add testing commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deployment commands (e.g., Docker, SCP, Kubernetes)
            }
        }
    }
}
