pipeline {
  agent {
    node {
      label 'ladh2427'
    }

  }
  stages {
    stage('Print Message') {
      steps {
        echo 'Test Jenkins'
        retry(count: 2)
      }
    }

  }
}