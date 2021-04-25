pipeline {
    agent any
    stages {
        stage('checkout git') {
            steps {
                git branch: branch, credentialsId: 'GitCredentials', url: scmUrl
            }
        }

        stage('build') {
            steps {
                sh './gradlew build --no-daemon'
            }
        }
    }
  
  post {
    always {
      archiveArtifacts artifacts: 'dist/trainSchedule.zip'
    }
  }  
}
