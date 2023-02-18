pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'
        echo 'Build successful'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        echo 'Test successful'
      }
    }
    stage('Deploy') {
      steps {
        sh 'mvn deploy'
        echo 'Deployment successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
