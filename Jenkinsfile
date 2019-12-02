pipeline {
  agent any
  environment {
         PATH = "C:\\Program Files\\Git\\usr\\bin;C:\\Program Files\\Git\\bin;${env.PATH}"
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
       
    stage('Deploy CloudHub') {
       steps {
        sh 'mvn deploy -P cloudhub -Danypoint.username=${ANYPOINT_CREDENTIALS_USR} -Danypoint.password=${ANYPOINT_CREDENTIALS_PSW}'
      }
    }
  }
}
