pipeline {
    agent any
    stages {
        stage('Setup Environment') {
            steps {
                echo "Checking Python version..."
                sh 'python3 --version || echo "Python not installed"'
            }
        }
        stage('Build') {
            steps {
                echo "Building..."
                sh '''
                python3 -m pip install --upgrade pip
                python3 -m pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Running Tests..."
                sh 'python3 test_script.py'
            }
        }
        stage('Deliver') {
            steps {
                echo "Delivery complete!"
            }
        }
    }
}


