pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        slackSend(color: '#FFFF00', message: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
        emailext(subject: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'", body: """<p>STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
            <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""", recipientProviders: [[$class: 'DevelopersRecipientProvider']])
      }
    }
    stage('Build') {
      steps {
        echo 'Building My career'
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          environment {
            Var14Test1 = 'Subash'
          }
          steps {
            echo 'Taking Tests to prove myself'
            sh '''ls -ltr / >> Test1.out
            ls -ltr /tmp >> Test2.out
            echo $Var14Test1 >> Test3.out'''
            archiveArtifacts(artifacts: 'Test*.out', fingerprint: true)
            stash(name: 'StashTest', includes: 'Test*.out')
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
        unstash 'StashTest'
        sh 'cat Test*'
      }
    }
    stage('error') {
      steps {
        input(message: 'Ticket approved?', ok: 'Yes')
      }
    }
  }
}