pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build and Package') {
            steps {
                script {
                    echo 'Building and packaging the application...'
                    sh 'docker build -t node-docker .'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the application...'
                    sh 'docker run -p 80:80 -d --name my-app2 node-docker'
                }
            }
        }
    }
}
