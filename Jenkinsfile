pipeline {
    agent {
      node 'slave'
      docker {
        image 'maven:3-alpine'
      }
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World $(hostname)"'
            }
        }
    }
}
