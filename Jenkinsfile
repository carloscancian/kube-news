pipeline {
    agent any

    stages {
        stage ('Build Docker Image') {
            steps{
                script{
                    dockerapp = docker.build("carloscancian/kubenews:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }
    }
}