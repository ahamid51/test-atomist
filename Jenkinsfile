pipeline {
  agent {
    node {
      label 'mashdev02'
    }

  }
  stages {
    stage('Stage1') {
      steps {
        echo 'Stage 1'
      }
    }

    stage('Stage2') {
      steps {
        echo 'Stage 2'
      }
    }

    stage('Stage3') {
      environment {
        envVariable = '1'
      }
      parallel {
        stage('Stage3') {
          steps {
            echo 'Stage 3'
            node(label: 'mashdev03') {
              sh '''pwd
whoami'''
            }

          }
        }

        stage('Stage4') {
          steps {
            echo 'Stage 4'
          }
        }

      }
    }

    stage('Stage5') {
      steps {
        echo 'Stage 5'
      }
    }

  }
}