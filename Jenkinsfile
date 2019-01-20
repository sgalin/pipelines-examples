pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          agent {
            docker {
              image 'maven:3-alpine'
              label 'slave'
            }
          }
          steps {
            sh 'echo "Hello World $(hostname)"'
            sleep 2
            sh ./test.sh
          }
        }
        stage('parallel') {
          agent {
            node {
              label 'master'
            }

          }
          steps {
            sh 'echo "Hello $(hostname)"'
            echo 'paralelo'
          }
        }
      }
    }
  }
}
