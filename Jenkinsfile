pipeline {
    agent any

    environment {
        username = 'user1'
        password = '111'
        userInputName = ''
        userInputPassword = ''
    }

    stages {
        stage("Get User Credentials") {
            steps {
                script {
                    // Prompt user for input and store it in environment variables
                    def userInput = input(
                        message: 'Enter credentials',
                        parameters: [
                            string(name: 'userInputName', defaultValue: '', description: 'Enter username'),
                            password(name: 'userInputPassword', defaultValue: '', description: 'Enter password')
                        ]
                    )

                    // Set environment variables for later stages
                    env.userInputName = userInput.userInputName
                    env.userInputPassword = userInput.userInputPassword

                    // Compare entered credentials with stored values
                    if (env.userInputName != username || env.userInputPassword != password) {
                        error "Invalid username or password. Pipeline will not proceed."
                    }
                }
            }
        }

        stage("Build") {
            when {
                expression {
                    // Ensure credentials were validated in the previous stage
                    return env.userInputName == username && env.userInputPassword == password
                }
            }
            steps {
                echo "Build is successful."
            }
        }

        stage("Stage") {
            when {
                expression {
                    return env.userInputName == username && env.userInputPassword == password
                }
            }
            steps {
                echo "Stage executed."
            }
        }

        stage("Check") {
            when {
                expression {
                    return env.userInputName == username && env.userInputPassword == password
                }
            }
            steps {
                echo "Check stage executed."
            }
        }

        stage("Develop") {
            when {
                expression {
                    return env.userInputName == username && env.userInputPassword == password
                }
            }
            steps {
                echo "Develop stage executed."
            }
        }
    }
}
