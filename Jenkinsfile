pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/oriax18/ci-cd-python-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp ./app'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                    docker stop myapp || true
                    docker rm myapp || true
                    docker run -d -p 8000:3000 --name myapp myapp
                '''
            }
        }
    }
}
