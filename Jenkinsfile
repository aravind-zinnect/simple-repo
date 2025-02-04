pipeline {
    agent any

    parameters {
        string(name: 'USERNAME', defaultValue: '', description: 'Enter Username')
        password(name: 'PASSWORD', defaultValue: '', description: 'Enter Password')
    }

    environment {
        validUsername = 'user1'
        validPassword = '111'
    }

    stages {
        stage("Check Credentials") {
            steps {
                script {
                    def username = params.USERNAME
                    def password = params.PASSWORD

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
