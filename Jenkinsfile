pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building My career'
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Taking Tests to prove myself'
          }
        }
        stage('Parallel Test') {
          steps {
            echo 'Taking Parallel Tests too.'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'What to deployed in international travel job'
      }
    }
  }
}