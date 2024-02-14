pipeline {
    agent any
    stages {
        stage('One') {
            steps {
                echo 'Hi, this is first pipeline'
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
                // stage('Integration test') {
                //     agent {
                //         docker {
                //             reuseNode true
                //             image 'ubuntu'
                //         }
                //     }
                //     steps {
                //         echo "Running the integration test..."
                //     }
              //
            //}
        }
    }
}