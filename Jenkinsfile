pipeline {
     agent {
        docker {
            image 'node:7'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo "hello,world."
            }
        }
        stage('Test') {
            steps {
                echo "test starting..."
            }
        }
        stage('Push') {
            steps {
                sh 'echo "Hello world!"'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                echo "push ended..."
            }
        }
    }
}
