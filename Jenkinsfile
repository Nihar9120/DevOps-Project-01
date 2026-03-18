pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Nihar9120/DevOps-Project-01.git'
            }
        }

        stage('Build Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-webapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:8080 devops-webapp'
            }
        }

    }
}
