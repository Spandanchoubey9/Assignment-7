
pipeline {
    agent any

    environment {
        KUBECONFIG = 'C:\\Users\\spand\\.kube\\config'
    }

    stages {

        stage('Pull Code') {
            steps {
                echo 'Source code is ready'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t assignment-7-app .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
                bat 'kubectl apply -f service.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                bat 'kubectl get deployments'
                bat 'kubectl get pods'
                bat 'kubectl get services'
            }
        }
    }
}
