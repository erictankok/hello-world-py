pipeline {
    agent { docker 'erictankok/docker:hello-world-py' }
    stages {
        stage('Build') {
            steps {
                sh 'python --version && id'
                sh 'ps -ef'
            }
        }
        stage('Stage') {
            steps {
                sh 'python hello-world.py'
                sh 'ps -ef'
            }
 	}
        stage('Test') {
            steps {
                sh 'while ! curl --output /dev/null --silent --head --fail http://localhost:8888; do sleep 1 && echo -n .; done'
            }
        }
    }
}
