pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'
        echo 'Build Successful'
      }
    } 
    stage('Test') {
      steps {
        sh 'mvn test'
        echo 'Test Successful'
        post {
          always {
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'mvn deploy'
        echo 'Deployment Successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
