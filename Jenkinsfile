pipeline {
    agent {
      docker {
        label 'slave'
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
