pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('Parallel-A') {
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
        stage('Parallel-B') {
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
    stage('Ansible') {
      agent{
        node{
          label 'slave'
        }
      }
      steps {
        ansiblePlaybook(playbook: 'play.yml')
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
