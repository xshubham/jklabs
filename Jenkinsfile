/* Requires the Docker Pipeline plugin */
pipeline {
    agent { 
        docker { 
            image 'python:3.13.3-alpine3.21' 
            args '--host=tcp://localhost:2375'
        } 
    }
    stages {
        stage('build') {
            steps {
                sh 'python3 main.py'
            }
        }
    }
}
