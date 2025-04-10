pipeline {
    agent {
        docker {
            image 'docker:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Build Docker Image') {
            steps {
                dir('app') {
                    sh 'docker build -t myapp .'
                }
            }
        }

        stage('Run App Container') {
            steps {
                sh 'docker run -d -p 8000:3000 --name myapp myapp || true'
            }
        }
    }
}
