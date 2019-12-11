pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "hello,world."
                sh "docker build -t caoyihong/kubia:${BUILD_ID} ."
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
                input message: '确定要发布镜像吗？'
                echo "push ended..."
            }
        }
    }
}
