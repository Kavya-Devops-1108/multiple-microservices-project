pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                        sh "docker build -t kavya318506/productcatalogservice:latest ."
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push kavya318506/productcatalogservice:latest "
                    }
                }
            }
        }
    }
}
