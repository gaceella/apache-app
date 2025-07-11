pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/gaceella/apache-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("gaceella/apache-app")
                }
            }
        }

        stage('Run Container for Testing') {
            steps {
                script {
                    dockerImage.run('-d -p 8080:80')
                }
            }
        }
    }
}

