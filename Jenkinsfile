pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your version control system (e.g., Git)
                git 'https://github.com/yourusername/your-maven-project.git'
            }
        }
        
        stage('Build') {
            steps {
                // Build the Maven project
                sh 'mvn clean package'
            }
        }
        
        stage('Unit Tests') {
            steps {
                // Run unit tests
                sh 'mvn test'
            }
        }
        
        stage('Integration Tests') {
            steps {
                // Run integration tests
                sh 'mvn integration-test'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the Maven project (e.g., to a repository, server, etc.)
                sh 'mvn deploy'
            }
        }
    }
}
