pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
      post {
        always {
             junit '**/target/surefire-reports/TEST-*.xml'
        }
    }
  }
}
