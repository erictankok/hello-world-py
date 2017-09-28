pipeline {
    agent { docker 'erictankok/docker:hello-world-py' }
    stages {
        stage('Build') {
            steps {
                sh 'python --version && id'
            }
        }
        stage('Test') {
            steps {
                sh 'for i in {1..5} ; do curl http://localhost ; done'
            }
        }
    }
}
