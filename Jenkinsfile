pipeline {
  agent any

  stages {
    stage('Hello world') {
      when {
        anyof {
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
