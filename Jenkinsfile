pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t katukutibalaji/paymentservice:v1 .'
            }
        }
        stage ('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub-cred') {
                         sh 'docker push katukutibalaji/paymentservice:v1'
                    }
                }
            }
        }
    }
}
