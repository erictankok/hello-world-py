pipeline {
    agent { docker 'python:2.7-slim' }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'pip install -r requirements.txt'
                sh 'python hello-world.py'
            }
        }
    }
}
