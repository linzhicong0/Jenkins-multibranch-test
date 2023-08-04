pipeline {
  agent any

  stages {
    stage('Hello world') {
      when {
        branch 'dev' 'uat' 'pre-prod'
      }
      steps{
        sh 'echo hello'
      }
    }
  }
}
