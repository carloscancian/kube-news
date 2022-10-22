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

        stage ('Push Image DockerHub') {
            steps{
                script{
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub' )
                        dockerapp.push('latest')
                        dockerapp.push("${env.BUILD_ID}")
                }
            }
        }
    }
}