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
                    # Create a virtual environment in the workspace
                    python3 -m venv .venv

                    # Activate it
                    . .venv/bin/activate

                    # Install dependencies into the venv
                    python -m pip install --upgrade pip
                    pip install -r requirements.txt 

                    # Run tests with coverage
                    pytest tests/ -v --cov=src
                '''
            }
        }
    }
}
