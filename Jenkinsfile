pipeline {
  agent any
  stages {
    stage('Set up') {
      steps {
        build 'app-testing/1.ecp-cli-setup/'
      }
    }
    stage('Credentials') {
      steps {
        build 'app-testing/2.ecp-cli-setup-configuration'
      }
    }
    stage('Application') {
      steps {
        build 'app-testing/3.ecp-cli-add-application'
      }
    }
    stage('Deployment') {
      steps {
        build 'app-testing/4.ecp-cli-create-deployment'
      }
    }
    stage('Stop deployment') {
      steps {
        build 'app-testing/5.ecp-cli-stop-deployment'
      }
    }
    stage('Remove App') {
      environment {
        ecp = '/home/ubuntu/ecp-cli/ecp.py'
      }
      steps {
        build 'app-testing/6.ecp-cli-remove-application'
      }
    }
    stage('Clean up') {
      steps {
        build 'app-testing/7.ecp-cli-cleanup'
      }
    }
  }
  environment {
    ecp_user = 'gianni'
  }
}
