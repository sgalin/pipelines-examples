pipeline {
  agent none
  stages {
    stage('A') {
      parallel {
        stage('Build') {
          agent {
            docker {
              image 'maven:3-alpine'
              label 'slave'
            }

          }
          steps {
            sleep 2
            echo 'Parallel A'
            sleep 15
          }
        }
        stage('B') {
          agent {
            node {
              label 'master'
            }

          }
          steps {
            echo 'Parallel B'
          }
        }
      }
    }
    stage('Publish') {
      steps {
        archiveArtifacts 'py'
      }
    }
    stage('Deploy-Dev') {
      steps {
        echo 'Deploy-Dev'
      }
    }
    stage('Deploy-UAT') {
      steps {
        echo 'Deploy-UAT'
      }
    }
    stage('Deploy-PRO') {
      steps {
        echo 'Deploy-PRO'
      }
    }
  }
}