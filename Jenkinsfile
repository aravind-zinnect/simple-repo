pipeline {
    agent any

    parameters {
        string(name: 'USERNAME', defaultValue: '', description: 'Enter Username')
        password(name: 'PASSWORD', defaultValue: '', description: 'Enter Password')
    }

    environment {
        validUsername = 'user1'
        // Use credentials from Jenkins' Credentials Manager
        validPassword = credentials('my-jenkins-password-id')  // Replace with your actual credential ID
    }

    stages {
        stage("Check Credentials") {
            steps {
                script {
                    def username = params.USERNAME
                    def password = params.PASSWORD

                    // Compare entered username and password
                    if (username != validUsername || password != validPassword) {
                        error "Invalid username or password. Pipeline will not proceed."
                    }
                }
            }
        }

        stage("Build") {
            when {
                expression { 
                    return params.USERNAME == validUsername && params.PASSWORD == validPassword 
                }
            }
            steps {
                echo "build......."
            }
        }

        stage("Stage") {
            when {
                expression { 
                    return params.USERNAME == validUsername && params.PASSWORD == validPassword 
                }
            }
            steps {
                echo "stage......."
            }
        }

        stage("Check") {
            when {
                expression { 
                    return params.USERNAME == validUsername && params.PASSWORD == validPassword 
                }
            }
            steps {
                echo "check......."
            }
        }

        stage("Develop") {
            when {
                expression { 
                    return params.USERNAME == validUsername && params.PASSWORD == validPassword 
                }
            }
            steps {
                echo "develop......."
            }
        }
    }
}
