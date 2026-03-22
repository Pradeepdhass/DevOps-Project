pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "yourdockerhubusername/ci-cd-app"
    }

    stages {

        stage('Clone') {
            steps {
                git 'git 'https://github.com/Pradeepdhass/jenkins.git''
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${DOCKER_IMAGE}")
                }
            }
        }

        stage('Push to DockerHub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-credentials',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {
                    sh "echo $PASS | docker login -u $USER --password-stdin"
                    sh "docker push ${DOCKER_IMAGE}:latest"
                }
            }
        }
    }
}
