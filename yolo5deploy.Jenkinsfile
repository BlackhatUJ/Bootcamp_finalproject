pipeline {
    agent any
    parameters { string(name: 'YOLO5_IMAGE_URL', defaultValue: '', description: '') }
    stages {
        stage('Deploy') {
            steps {
                
                sh '''
                aws eks --region us-east-2 update-kubeconfig --name k8s-batch1
                kubectl config set-context --current --namespace=ujjwal
                kubectl apply -f Yolo5.yaml
                '''
            }
        }
    }
}