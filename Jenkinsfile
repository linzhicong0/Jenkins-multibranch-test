pipeline {
  agent any
  environment {
    NAME_dev = 'DEV'
    NAME_uat = 'UAT'
    'NAME_pre-prod' = 'PRE_RPDO'
    NAME_prod = 'PROD'
  }
  stages {
    stage('Hello world') {
      when {
        anyOf {
          branch 'dev';
          branch 'uat';
          branch 'pre-prod'
        }
      }
      environment {
        NAME = ${'NAME_'${BRANCH_NAME}}
      }
      steps{
        sh 'echo ${NAME}'
      }
    }
  }
}
