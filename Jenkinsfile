pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                sh '''
                aws eks update-kubeconfig --region ap-southeast-2 --name sydney-cluster-4
                kubectl apply -f deployment-service.yml
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                sh '''
                kubectl get svc -n webapps
                '''
            }
        }
    }
}
