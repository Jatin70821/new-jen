pipeline {

    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Jatin70821/new-jen'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mysite .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker stop mysite-container || true'
                sh 'docker rm mysite-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 80:80 --name mysite-container mysite'
            }
        }
    }
}