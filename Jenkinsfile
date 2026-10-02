
pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Mns123455/docker-python-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t my-python-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'sudo docker stop my-python-container || true'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'sudo docker rm my-python-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'sudo docker run -d -p 5000:5000 --name my-python-container my-python-app'
            }
        }
    }
}
