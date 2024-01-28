pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                sh 'yocto build command here'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
            }
        }
        
        stage('SonarQube Analysis') {
            steps {
                script {
                    withSonarQubeEnv('SonarQubeServer') {
                        sh 'sonar-scanner command here'
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy artifacts
            }
        }
    }
    
    post {
        always {
            // Clean up or notify
        }
    }
}
