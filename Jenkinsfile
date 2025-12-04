pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t katukutibalaji/productcatalogservice:v1 .'
            }
        }
        stage ('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerHub-ID') {
                         sh 'docker push katukutibalaji/productcatalogservice:v1'
                    }
                }
            }
        }
    }
}
