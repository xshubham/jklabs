/* Requires the Docker Pipeline plugin */
pipeline {
    agent { 
        docker { image 'python:3.13.3-alpine3.21' }
    }
    environment {
        DOCKER_HOST = 'tcp://localhost:2375'
    }
    stages {
        stage('build') {
            steps {
                sh 'python3 main.py'
            }
        }
    }
}
