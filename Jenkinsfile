pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Meenusree9482002/jenkins-101'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                    echo "Building Docker image..."
                    docker build -t hello-world-app .
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                    echo "Running Docker container..."
                    docker run --rm hello-world-app
                '''
            }
        }
    }

    post {
        always {
            sh 'echo "Pipeline execution completed."'
        }
    }
}
