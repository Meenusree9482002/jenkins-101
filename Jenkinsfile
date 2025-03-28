pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Meenusree9482002/jenkins-101'
            }
        }

        stage('Setup Environment') {
            steps {
                sh '''
                echo "Setting up Python environment..."
                
                # Install Python if not available
                if ! command -v python3 &> /dev/null; then
                    echo "Python not found. Installing..."
                    apt update && apt install -y python3 python3-pip python3-venv
                fi
                
                # Create virtual environment
                python3 -m venv venv
                source venv/bin/activate

                echo "Python Version:"
                python3 --version
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                source venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt  # Install dependencies
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                source venv/bin/activate
                python3 -m unittest discover tests
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step goes here...'
            }
        }
    }

    post {
        always {
            sh 'deactivate || true'  # Ensure the virtual environment is deactivated
        }
    }
}



