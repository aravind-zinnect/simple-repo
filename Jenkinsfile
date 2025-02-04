

pipeline {
    agent any

    environment {
        username = 'user1'
        password = '111'
    }

    stages {
        stage("Get User Credentials") {
            steps {
                script {
                    // Prompt user for input
                    def userInput = input(
                        message: 'Enter credentials',
                        parameters: [
                            string(name: 'userInputName', defaultValue: '', description: 'Enter username'),
                            password(name: 'userInputPassword', defaultValue: '', description: 'Enter password')
                        ]
                    )

                    // Compare entered credentials with stored values
                    if (userInput.userInputName != username || userInput.userInputPassword != password) {
                        error "Invalid username or password. Pipeline will not proceed."
                    }
                }
            }
        }

        stage("Build") {
            when {
                expression {
                    // Ensure credentials were validated in the previous stage
                    return userInput.userInputName == username && userInput.userInputPassword == password
                }
            }
            steps {
                echo "Build is successful."
            }
        }

        stage("Stage") {
            when {
                expression {
                    return userInput.userInputName == username && userInput.userInputPassword == password
                }
            }
            steps {
                echo "Stage executed."
            }
        }

        stage("Check") {
            when {
                expression {
                    return userInput.userInputName == username && userInput.userInputPassword == password
                }
            }
            steps {
                echo "Check stage executed."
            }
        }

        stage("Develop") {
            when {
                expression {
                    return userInput.userInputName == username && userInput.userInputPassword == password
                }
            }
            steps {
                echo "Develop stage executed."
            }
        }
    }
}
