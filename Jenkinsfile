pipeline {
  agent any
  stages {
    stage('A1') {
      parallel {
        stage('A1') {
          steps {
            echo '11'
          }
        }
        stage('A2') {
          steps {
            echo '22'
          }
        }
      }
    }
  }
}