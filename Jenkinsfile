pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Deploy') {
      when {
        branch 'master'
      }
      steps {
        sh './mvnw deploy'
      }
    }

  }
  post{
    success{
      slackSend channel: 'soen345', message: 'Success', tokenCredentialId: '38d25e02-a91f-41ee-be54-5a6b62a24687'
    }
    
    failure{
      slackSend channel: 'soen345', message: 'Failed', tokenCredentialId: '38d25e02-a91f-41ee-be54-5a6b62a24687'      
    }
  }
}
}
