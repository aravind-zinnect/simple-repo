
pipeline {
    agent any
    parameters {
        string(name: 'USERNAME', defaultValue: '', description: 'Enter your username')
        password(name: 'PASSWORD', defaultValue: '', description: 'Enter your password')
    }

    stages {
        stage("Check Credentials") {
            steps {
                script {
                    if (params.USERNAME != 'user1' || params.PASSWORD != '111') {
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
