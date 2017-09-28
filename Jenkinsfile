pipeline {
    agent { docker 'erictankok/docker:hello-world-py' }
    stages {
        stage('Build') {
            steps {
                sh 'python --version && id'
                sh 'ps -ef'
            }
        }
        stage('Test') {
            steps {
                sh 'while ! curl --output /dev/null --silent --head --fail http://localhost; do sleep 1 && echo -n .; done'
            }
        }
    }
}
