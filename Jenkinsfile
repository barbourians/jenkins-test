pipeline {
    agent {
        docker {
            image 'python:3.12'
        }
    }

    stages {
        stage('Install dependencies') {
            steps {
                sh '''
                    python -m pip install --upgrade pip
                    pip install -r requirements.txt
                    pip install pytest pytest-cov
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
