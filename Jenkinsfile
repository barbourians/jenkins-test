pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                echo 'Repo cloned by Jenkins automatically'
            }
        }
        stage('Build') {
            steps {
                echo 'Running build steps...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'pytest tests/ -v --cov=src'
            }
        }
    }
}
