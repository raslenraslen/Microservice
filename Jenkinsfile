pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeConfig([credentialsId: 'k8s-token', contextName: 'kubernetes-admin@kubernetes']) {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        
        stage('Verify Deployment') {
            steps {
                withKubeConfig([credentialsId: 'k8s-token', contextName: 'kubernetes-admin@kubernetes']) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
