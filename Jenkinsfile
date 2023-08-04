pipeline {
  agent any
  environment {
    NAME_dev = 'DEV'
    NAME_uat = 'UAT'
    NAME_pre_prod = 'PRE_RPDO'
    NAME_prod = 'PROD'
    NAME = ''
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
      steps{
        script {
          echo env.BRANCH_NAME
          if (env.BRANCH_NAME == 'dev'){
            env.NAME = env.NAME_dev
            echo env.NAME
          }
          if (env.BRANCH_NAME == 'uat'){
            env.NAME = env.NAME_uat
          }
          if (env.BRANCH_NAME == 'pre_prod'){
            env.NAME = env.NAME_pre_prod
          }

          echo NAME
        }
        
      }
    }
  }
}
