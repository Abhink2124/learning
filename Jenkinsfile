pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt || true
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                . venv/bin/activate
                python3 test_app.py
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                . venv/bin/activate
                python3 app.py > output.txt
                cat output.txt
                '''
            }
        }
    }
}
