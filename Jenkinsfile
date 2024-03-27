pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ravitejapamidi/pytest-intro-vs.git']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/ravitejapamidi/pytest-intro-vs.git'
                sh 'python3 ops.py'
            }
        }
        stage('Test') {
            steps {
                // Install dependencies before running tests
                sh 'pip install -r requirements.txt'
                // Run pytest
                sh 'python3 -m pytest'
            }
        }
    }
}
