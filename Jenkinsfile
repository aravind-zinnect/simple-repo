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
                    // Prompt user for username and password
                    def userInput = input message: 'Please enter credentials', parameters: [
                        string(name: 'Username', defaultValue: '', description: 'Enter Username'),
                        password(name: 'Password', defaultValue: '', description: 'Enter Password')
                    ]
                    
                    // Extract input values
                    def username = userInput['Username']
                    def password = userInput['Password']

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
