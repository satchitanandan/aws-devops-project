pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/satchitanandan/aws-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sachin-devops-project .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop sachin-container || true
                docker rm sachin-container || true
                docker run -d --name sachin-container -p 80:80 sachin-devops-project
                '''
            }
        }
    }
}
