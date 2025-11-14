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
                sh '''
                    python3 -m pip install --upgrade pip
                    python3 -m pip install -r requirements.txt 
                    pytest tests/ -v --cov=src
                '''
            }
        }
    }
}
