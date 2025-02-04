pipeline {
    agent any

    environment {
        validUsername = 'user1'
        validPassword = '111'
    }

    stages {
        stage("Check Credentials") {
            steps {
                script {
                    // Prompt the user to enter username and password
                    def userInput = input(
                        message: 'Please enter your credentials',
                        parameters: [
                            string(name: 'username', defaultValue: '', description: 'Enter username'),
                            password(name: 'password', defaultValue: '', description: 'Enter password')
                        ]
                    )
                    
                    def enteredUsername = userInput['username']
                    def enteredPassword = userInput['password']

                    // Check the credentials
                    if (enteredUsername != validUsername || enteredPassword != validPassword) {
                        error "Invalid username or password. Pipeline will not proceed."
                    }
                }
            }
        }

        stage("Build") {
            when {
                expression {
                    // Check if credentials are valid
                    return enteredUsername == validUsername && enteredPassword == validPassword
                }
            }
            steps {
                echo "Building......."
            }
        }

        stage("Stage") {
            when {
                expression {
                    return enteredUsername == validUsername && enteredPassword == validPassword
                }
            }
            steps {
                echo "Stage......."
            }
        }

        stage("Check") {
            when {
                expression {
                    return enteredUsername == validUsername && enteredPassword == validPassword
                }
            }
            steps {
                echo "Check......."
            }
        }

        stage("Develop") {
            when {
                expression {
                    return enteredUsername == validUsername && enteredPassword == validPassword
                }
            }
            steps {
                echo "Develop......."
            }
        }
    }
}
