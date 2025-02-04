pipeline {
    agent any

    environment {
        validUsername = 'user1'
        validPassword = '111'
    }

    stages {
        stage("Get Credentials") {
            steps {
                script {
                    // Dynamic input for username and password
                    def username = input message: 'Enter Username', parameters: [string(defaultValue: '', description: 'Enter your username', name: 'Username')]
                    def password = input message: 'Enter Password', parameters: [password(defaultValue: '', description: 'Enter your password', name: 'Password')]

                    // Check if the provided credentials are correct
                    if (username != validUsername || password != validPassword) {
                        error "Invalid username or password. Pipeline will not proceed."
                    }
                }
            }
        }

        stage("Build") {
            when {
                expression { 
                    return username == validUsername && password == validPassword 
                }
            }
            steps {
                echo "build......."
            }
        }
        
        stage("Stage") {
            when {
                expression { 
                    return username == validUsername && password == validPassword 
                }
            }
            steps {
                echo "stage......."
            }
        }

        stage("Check") {
            when {
                expression { 
                    return username == validUsername && password == validPassword 
                }
            }
            steps {
                echo "check......."
            }
        }

        stage("Develop") {
            when {
                expression { 
                    return username == validUsername && password == validPassword 
                }
            }
            steps {
                echo "develop......."
            }
        }
    }
}
