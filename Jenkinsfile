/* Requires the Docker Pipeline plugin */
pipeline {
    agent { 
        docker { image 'python:3.13.3-alpine3.21' }
    }
    stages {
        stage('build') {
            steps {
                script {
                    docker.build("jklabs:${env.BUILD_NUMBER}")
                }
            }
        }
        stage('test') {
            steps {
                script {
                    docker.image("jklabs:${env.BUILD_NUMBER}").run("--name jklabs_${env.BUILD_NUMBER}")
                }
            }
        }
    }
    post {
        always {
            script {
                sh "docker container rm jklabs_${env.BUILD_NUMBER}"
                echo "Completed Pipeline Execution!"
            }
        }
    }
}
