pipeline {
    agent any

    environment {
        validUsername = 'user1'
        validPassword = '111'
        validUsername2 = 'user2'
        validPassword2 = '222'
    }

    stages {
        stage("Check Credentials") {
            steps {
                script {
                    // Hardcoded credentials (for example purposes, set by the user or from a parameter)
                    def username = 'user1'  // Replace with dynamic value if needed
                    def password = '111'    // Replace with dynamic value if needed

                    // Check if the provided credentials match any valid set
                    if ((username == validUsername && password == validPassword) ||
                        (username == validUsername2 && password == validPassword2)) {
                        echo "Valid credentials: ${username}"
                    } else {
                        error "Invalid username or password. Pipeline will not proceed."
                    }
                }
            }
        }

        // If user1 credentials are valid, execute these stages
        stage("Build") {
            when {
                expression {
                    return (username == validUsername && password == validPassword)
                }
            }
            steps {
                echo "Build stage for user1"
            }
        }
        
        stage("Stage") {
            when {
                expression {
                    return (username == validUsername && password == validPassword)
                }
            }
            steps {
                echo "Stage for user1"
            }
        }

        // If user2 credentials are valid, execute these stages
        stage("Check") {
            when {
                expression {
                    return (username == validUsername2 && password == validPassword2)
                }
            }
            steps {
                echo "Check stage for user2"
            }
        }

        stage("Develop") {
            when {
                expression {
                    return (username == validUsername2 && password == validPassword2)
                }
            }
            steps {
                echo "Develop stage for user2"
            }
        }
    }
}
