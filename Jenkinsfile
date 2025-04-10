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

    }
}
