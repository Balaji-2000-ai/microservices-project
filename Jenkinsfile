pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t katukutibalaji/emailservice:v1 .'
            }
        }
        stage ('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerHub-ID') {
                         sh 'docker push katukutibalaji/emailservice:v1'
                    }
                }
            }
        }
    }
}
