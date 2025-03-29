pipeline {
    agent any

    stages {
        stage('Initialize') {
            steps {
                echo 'Initializing Pipeline for MyProject...'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'echo Compiling source code...'
                sh 'python3 helloworld.py' // Execute the script
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo Executing unit tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'echo Deploying to production...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished. Cleaning up...'
        }
        success {
            echo 'Pipeline execution completed successfully!'
        }
    }
}

