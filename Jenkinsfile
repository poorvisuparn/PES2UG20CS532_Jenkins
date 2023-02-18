pipeline {
agent any
stages {
    stage('Build') {
        steps {
            sh 'g++ -o PES2UG20CS532-1/main/hello.cpp'
        }
    }
    
    stage('Test') {
        steps {
            sh './PES2UG20CS532-1'
        }
    }
    
    stage('Deploy') {
        steps {
            // deployment code
            sh 'mvn deploy'
            echo 'deployment successful'
        }
    }
}

post {
    always {
        script {
            if (currentBuild.result == "FAILURE") {
                echo "Pipeline failed"
            }
        }
    }
}
}
