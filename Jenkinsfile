pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t katukutibalaji/cartservice:v1 src'
            }
        }
        stage ('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub-cred') {
                         sh 'docker push katukutibalaji/cartservice:v1'
                    }
                }
            }
        }
    }
}
