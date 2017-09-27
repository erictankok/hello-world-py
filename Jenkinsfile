pipeline {
    agent { docker 'python:2.7-slim' }
    stages {
        stage('build') {
            steps {
                sh 'python --version && id'
                sh 'pip list'
                sh 'pip install --user -r requirements.txt'
                sh 'python hello-world.py'
            }
        }
    }
}
