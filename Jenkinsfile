pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'mvn clean'
      }
    }

    stage('Test') {
      steps {
        bat 'mvn test'
      }
    }

    stage('notify') {
      steps {
        emailext(subject: 'Build report', body: 'Please visit ${env.BUILD_URL} for further information', attachLog: true, attachmentsPattern: '.html', replyTo: 'prasad.satya0119@gmail.com', to: 'prasad.satya0119@gmail.com')
      }
    }

  }
}