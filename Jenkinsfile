  pipeline {
    agent any
    

    stages {
    

        stage('Build') {
            steps {
                script {
                        // Source the build environment
                        sh 'bash -c "source oe-init-build-env"'
                        
                        // Build the project using bitbake
                        sh 'bash -c "bitbake core-image-sato"'
            }
        }

        stage('Sonar') {
            steps {
                script {
                    // Run SonarQube scanner
                    sh 'sonar-scanner ' +
                       '-Dsonar.projectKey=test-task ' +
                       '-Dsonar.sources=. ' +
                       '-Dsonar.host.url=http://192.168.0.133:9000 ' +
                       '-Dsonar.token=sqp_c0b1923f892be76001a0adc2dcfc537e452bf817'
                }
            }
        }
    }
}
