pipeline {
    agent any
    stages {
        stage('Setup Environment') {
            steps {
                sh '''
                if ! command -v python3 &> /dev/null
                then
                    echo "Python not installed. Installing now..."
                    apt update && apt install -y python3 python3-pip
                fi
                python3 --version
                '''
            }
        }
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


