pipeline {
    agent any  // Runs on any available agent
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Setup Environment') {
            steps {
                echo "Installing Python..."
                sh '''
                apt update && apt install -y python3 python3-pip
                python3 --version
                pip3 --version
                '''
            }
        }
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                python3 -m pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}

