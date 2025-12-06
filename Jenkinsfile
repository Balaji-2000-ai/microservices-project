pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'katukutibalaji.k8s.local', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-Cluster', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
