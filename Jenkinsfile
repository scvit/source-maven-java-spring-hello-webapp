pipeline {
  agent any

  triggers {
    pollSCM('* * * * *')
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', 
        url: 'https://github.com/scvit/source-maven-java-spring-hello-webapp'
      }
    }
    stage('Build') {
      steps {
        sh 'cat /etc/os-release'
      }
    }
    stage('Test') {
      steps {
        sh 'java --version'
      }
    }
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'admin', url: 'http://43.202.164.13:8080')], contextPath: null, war: 'path/to/war'
      }
    }
  }
}