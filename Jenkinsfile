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
                echo "Hello world."
                input message: '确定要发布镜像吗？'
                withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
                  echo "测试账号---"
                  echo ${dockerHubUser}
                  echo ${dockerHubPassword}
                  sh "docker login -u ${dockerHubUser} -p ${dockerHubPassword}"
                  sh "docker push caoyihong/kubia:${BUILD_ID}"
                }
                echo "push ended..."
            }
        }
    }
}
