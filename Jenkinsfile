pipeline {
    agent any
    


    stages {
        /* stage('Build') {
            steps {
                script {
                    // Change to your build workspace

                        // Source the build environment using Bash
                        sh 'bash -c "source oe-init-build-env && bitbake core-image-sato"'
                        
                        // Archive the built image
                        archiveArtifacts artifacts: '/var/lib/jenkins/workspace/test/core-image-sato-*.tar.gz', fingerprint: true
                    
                    
                }
            }
        } */

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
