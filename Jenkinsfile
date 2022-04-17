pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git 'https://github.com/hatamoni/springbootappdemo.git'
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
             mail bcc: '', body: 'Mail from Jenkins huuhuuu', cc: '', from: '', replyTo: '', subject: 'Build Successful', to: 'jenkins@jenkins.master.hix'
             
        }
      }
    }
  }
}
