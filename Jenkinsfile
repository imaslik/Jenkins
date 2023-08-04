pipeline {
  agent none
  stages {
    stage('Print Message') {
      steps {
        echo 'Test Jenkins'
        retry(count: 2)
      }
    }

  }
}