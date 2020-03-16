pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

  }
  post {
    success {
      slackSend(channel: 'général', message: 'Success', tokenCredentialId: '38d25e02-a91f-41ee-be54-5a6b62a24687')
    }

    failure {
      slackSend(channel: 'général', message: 'Failed', tokenCredentialId: '38d25e02-a91f-41ee-be54-5a6b62a24687')
    }

  }
}