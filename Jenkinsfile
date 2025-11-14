pipeline {
    agent any

    stages {
        stage('Install Python') {
            steps {
                sh '''
                    apt-get update
                    apt-get install -y python3 python3-pip
                '''
            }
        }

        stage('Install dependencies') {
            steps {
                sh '''
                    python3 -m pip install --upgrade pip
                    pip3 install -r requirements.txt
                    pip3 install pytest pytest-cov
                '''
            }
        }

        stage('Run tests') {
            steps {
                sh 'pytest tests/ -v --cov=src --cov-report=term-missing'
            }
        }

        stage('Check test coverage') {
            steps {
                sh 'coverage report --fail-under=70'
            }
        }
    }
}
