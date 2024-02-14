pipeline {
    agent any
    stages {
        stage('One') {
            steps {
                echo 'Hi, this is pipeline demo'
            }
        }
        stage('Two') {
            steps {
                input 'Do you want to proceed?'
            }
        }
        stage('Three') {
            when {
                expression {
                    return env.BRANCH_NAME == 'main'
                }
            }
            steps {
                echo "Hello"
            }
        }
        stage('Four') {
            parallel {
                stage('Unit Test') {
                    steps {
                        echo "Running the unit test..."
                    }
                }
                stage('Security Test') {
                    steps {
                        echo "Running security tests..."
                        sh 'echo "Running security test"'
                    }
                }
            }
        }
    }
}

