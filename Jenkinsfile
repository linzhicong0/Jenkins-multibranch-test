pipeline {
  agent any
  environment {
    NAME_dev = 'DEV'
    NAME_uat = 'UAT'
    NAME_pre_prod = 'PRE_RPDO'
    NAME_prod = 'PROD'
  }
  stages {
    stage('Set Variables For Non-Prod') {
      when {
        anyOf {
          branch 'dev';
          branch 'uat';
          branch 'pre-prod'
        }
      }
      steps{
        script {
          if (env.BRANCH_NAME == 'dev'){
            env.NAME = env.NAME_dev
          }
          if (env.BRANCH_NAME == 'uat'){
            env.NAME = env.NAME_uat
          }
          if (env.BRANCH_NAME == 'pre_prod'){
            env.NAME = env.NAME_pre_prod
          }

        }
      }
    }
        stage('Set Variables For Prod') {
      when {
          branch 'main'
      }
      steps{
        script {
          env.NAME = env.NAME_prod
        }
      }
    }
    stage('Build') {
      steps {
        script {
          echo env.NAME
        }
      }
    }
  }
}
