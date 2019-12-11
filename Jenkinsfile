pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './scripts/build.sh'
            }
        }
        stage('Test') {
            steps {
                sh './scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh 'echo "Hello world!"'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './scripts/deploy.sh'
            }
        }
    }
}
