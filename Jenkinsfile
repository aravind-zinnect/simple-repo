pipeline {
    agent any

    stages {
        stage("Check Credentials") {
            steps {
                script {
                    // Hardcoded credentials (username: 'user1' and password: '111')
                    def username = 'user1'
                    def password = '111'

                    // Check if the provided credentials are correct
                    if (username != 'user11' || password != '1111') {
                        error "Invalid username or password. Pipeline will not proceed."
                    }
                }
            }
        }

        stage("Build") {
            steps {
                echo "build......."
            }
        }
        stage("Stage") {
            steps {
                echo "stage......."
            }
        }
        stage("Check") {
            steps {
                echo "check......."
            }
        }
        stage("Develop") {
            steps {
                echo "develop......."
            }
        }
    }
}
