pipeline {
    agent {label 'ec2-jenkins'}

    stages {
        stage('Git checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/himansharma23/fusionpact-devops-challenge.git'
            }
        }

        stage('Build') {
            steps {
                sh 'cd backend && sudo docker build -t himansh2k3/fusionpact-backend:$BUILD_ID .'
                sh 'cd backend && sudo docker build -t himansh2k3/fusionpact-frontend:$BUILD_ID .'
            }
        }

        stage('Image Push') {
            steps {
                sh 'sudo docker push himansh2k3/fusionpact-backend:$BUILD_ID'
                sh 'sudo docker push himansh2k3/fusionpact-frontend:$BUILD_ID'
            }
        }
    }
}
