pipeline {
  agent {
    docker {
      label 'slave'
      image 'maven:3-alpine'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo "Hello World $(hostname)"'
            sleep 2
            sh 'echo "After sleep"'
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