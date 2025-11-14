pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build...'
            }
        }
        stage('Test') {
            steps {
                sh 'pip install -r requirements.txt'
                sh 'pytest tests/ -v --cov=src'
            }
        }
    }
}
