pipeline {
    agent any
    stages {
        stage('One') {
            steps {
                echo 'Hi, This is first Pipeline Demo'
                sh 'echo "Executing task one"'
            }
        }
        stage('Two') {
            steps {
                input 'Do you want to proceed?'
                sh 'echo "User input received, proceeding..."'
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
                sh 'echo "Executing task three on main branch"'
            }
        }
        stage('Four') {
            parallel {
                stage('Unit Test') {
                    steps {
                        echo "Running the unit test..."
                        sh 'echo "Running unit test"'
                    }
                }
                stage('Integration test') {
                    agent {
                        docker {
                            reuseNode true
                            image 'ubuntu'
                        }
                    }
                    steps {
                        echo "Running the integration test..."
                        sh 'echo "Running integration test"'
                    }
                }
                stage('Security test') {
                    steps {
                        echo "Running security tests..."
                        sh 'echo "Running security test"'
                    }
                }
            }
        }
    }
}
