pipeline {
  agent none
  stages {
    stage('Print Message') {
      steps {
        echo 'Test Jenkins'
      }
    }

    stage('Set Temp') {
      agent {
        node {
          label 'ladh2427'
        }

      }
      environment {
        temperature = '25'
      }
      steps {
        build 'actions/SetTemperature'
      }
    }

  }
}