pipeline {
    parameters {
        string(name: 'OS_PORT', defaultValue: '8888')
        string(name: 'CONTAINER_PORT', defaultValue: '8888')
   }
   agent { 
        docker {
            image 'erictankok/docker:hello-world-py'
            args '-p 8888:8888'
            // args '-p ${params.OS_PORT}:${params.CONTAINER_PORT}'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'python --version && id'
                sh 'ps -ef'
            }
        }
        stage('Stage') {
            steps {
                sh 'BUILD_ID=dontKillMe nohup python hello-world.py &'
                sh 'ps -ef'
            }
 	}
        stage('Test') {
            steps {
                sh "while ! curl --output /dev/null --silent --head --fail http://localhost:${params.CONTAINER_PORT}; do sleep 1 && echo -n .; done"
                sh 'echo Test: Success!'
            }
        }
    }
}
