pipeline {
agent any

    triggers {
        pollSCM('* * * * *')
    }


    stages {

        stage('Clear') {
            steps{
                sh '''
                    chmod +x clear.sh
                    ./clear.sh
                '''
            }
        }
        
        stage('Checkout') {
            steps {
                git 'https://github.com/Dawid511/ping-pong-java'
            }
        }
        
        stage('Build') {
            steps {
                echo "Build stage"
                sh './gradlew clean build'
                sh "docker build -t build_stage -f ./building/Dockerfile ."
            }
        }

        stage('Test') {
            steps {
                echo "Test stage"
                 sh "docker build -t test_stage -f ./test/Dockerfile ."
            }
        }

        stage('Prepare Deploy') {
            steps {
                echo "Prepare Deploy stage"
                sh 'cp build/libs/my-app-1.0.jar deploy/'
            }
        }

        stage('Deploy'){
            steps{
                echo "Deploy stage"
                sh "docker build --no-cache  -t deploy_stage -f ./deploy/Dockerfile ."
                sh "docker run --rm deploy_stage"
            }
        }    
    }

    post{
        success {
            echo 'Success'
        }
        failure {
            echo 'Failed'
        }
    }
    
}