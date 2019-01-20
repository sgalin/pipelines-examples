pipeline {
    agent {
      node 'slave'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World $(hostname)"'
            }
        }
    }
}
