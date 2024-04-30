pipeline {
agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        
        stage('Checkout') {
            steps {
                git 'https://github.com/Dawid511/ping-pong-java'
            }
        }
        
        stage('Build') {
            steps {
                echo "Build stage"
                sh "docker build -t pong -f ./building/Dockerfile ."
            }
        }

        stage('Test') {
            steps {
                echo "Test stage"
                 sh "docker build -t pong -f ./test/Dockerfile ."
            }
        }
     
    }
    post{
        asuccess {
            echo 'Success'
        }
        failure {
            echo 'Failed'
        }
    }
    
}