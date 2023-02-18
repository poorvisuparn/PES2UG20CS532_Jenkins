pipeline {
agent any
stages {
    stage('Build') {
        steps {
            sh 'g++ -o hello_output PES2UG20CS532-1/main/hello.cpp'
        }
    }
    
    stage('Test') {
        steps {
            sh './hello_output'
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
