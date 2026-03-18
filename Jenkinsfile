pipeline {
    agent any

    tools {
    jdk 'openjdk 17.0.18'
    maven 'Apache Maven 3.8.4'
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Nihar9120/DevOps-Project-01.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-webapp .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker rm -f my-container || true'
                sh 'docker run -d -p 8081:8080 --name my-container my-webapp'
            }
        }
    }
}
