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
          if (BRANCH_NAME == 'dev'){
            env.NAME = "${NAME_dev}"
          }
          if (BRANCH_NAME == 'uat'){
            env.NAME = "${NAME_uat}"
          }
          if (BRANCH_NAME == 'pre_prod'){
            env.NAME = "${NAME_pre_prod}"
          }          
        }
        sh 'echo ${NAME}'
      }
    }
  }
}
