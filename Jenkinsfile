pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 --version'  // Python version check
                sh 'pip3 install -r requirements.txt || true'  // Dependencies (if any)
            }
        }
        stage('Test') {
            steps {
                sh 'python3 test_app.py'  // Run tests
            }
        }
        stage('Deploy') {
            steps {
                sh 'python3 app.py > output.txt'  // Run app and save output
                sh 'cat output.txt'  // Display output
            }
        }
    }
}
