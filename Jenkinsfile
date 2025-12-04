pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-Cluster', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps', serverUrl: 'https://D59D2731203770D07B6EB0570FAD920E.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-Cluster', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps', serverUrl: 'https://D59D2731203770D07B6EB0570FAD920E.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
