pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build -t flask-jenkins-app .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Running Docker Container...'
                sh 'docker run -d -p 5000:5000 --name flask-jenkins-container flask-jenkins-app || true'
            }
        }
    }
}
