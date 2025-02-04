

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
                
                    def username = 'user1'
                    def password = '111'

             
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
