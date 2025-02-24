pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Imagee') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t raslenmissaoui061/adservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push raslenmissaoui061/adservice:latest "
                    }
                }
            }
        }
    }
}
