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
                sh "date"
                sh "yum -y install ntp"
                sh "ntpdate cn.pool.ntp.org"
                sh "date"
                withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
                  sh "docker login -u ${dockerHubUser} -p ${dockerHubPassword}"
                  sh "docker push caoyihong/kubia:${BUILD_ID}"
                }
                echo "push ended..."
            }
        }
    }
}
