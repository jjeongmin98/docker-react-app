pipeline {
    agent any

    stages {
        stage("Set Variable") {
            steps {
                script {
                    IMAGE_NAME = "docker-compose.yaml"
                    IMAGE_STORAGE = "Jenkinsfile"
                    IMAGE_STORAGE_CREDENTIAL = "jjeongmin98"
                    SSH_CONNECTION = "meme@49.142.7.24"
                    SSH_CONNECTION_CREDENTIAL = "deploy-server-ssh-credential"
                }
            }
        }

        stage("Clean Build Test") {
            steps {
                sh "./gradlew clean build test"
            }
        }
