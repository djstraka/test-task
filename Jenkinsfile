pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'source oe-init-build-env'
            sh '''bitbake core-image-sato
'''
          }
        }

        stage('sonar') {
          steps {
            sh '''sonar-scanner \\
  -Dsonar.projectKey=test-task \\
  -Dsonar.sources=. \\
  -Dsonar.host.url=http://192.168.0.133:9000 \\
  -Dsonar.token=sqp_c0b1923f892be76001a0adc2dcfc537e452bf817'''
          }
        }

      }
    }

  }
}