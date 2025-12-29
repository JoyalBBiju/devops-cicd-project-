pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/JoyalBBiju/devops-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-web-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f webapp || true
                docker run -d -p 8080:80 --name webapp devops-web-app
                '''
            }
        }
    }
}
