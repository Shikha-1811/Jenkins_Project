pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('Docker-creds') 
    }
    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main', git 'https://github.com/Shikha-1811/Jenkins_Project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t shikha1811/miniproject1:latest .'
            }
        }
        stage('Push to DockerHub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh 'docker push shikha1811/miniproject1:latest'
            }
        }
        stage('Deploy to EC2') {
            steps {
                sh '''
                docker rm -f website-container || true
                docker run -d -p 80:80 --name website-container shikha1811/miniproject1:latest
                '''
            }
        }
    }
}
