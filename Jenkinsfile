pipeline {
  agent any

  stages {
    stage('Hello world') {
      when {
        anyOf {
          branch 'dev';
          branch 'uat';
          branch 'pre-prod'
        }
        
      }
      steps{
        sh 'echo hello'
      }
    }
  }
}
