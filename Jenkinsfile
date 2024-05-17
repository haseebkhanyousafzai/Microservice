pipeline {
    agent any

    stages {
        stage('deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'kubernetes', namespace: 'webapps', serverUrl: 'https://A3D948CE3EC9E4AF1ACF8C8877FC0049.sk1.ap-south-1.eks.amazonaws.com']]) {
                sh "kubectl apply -f deployment-service.yml"
             }
            }
        }
        stage('test') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'kubernetes', namespace: 'webapps', serverUrl: 'https://A3D948CE3EC9E4AF1ACF8C8877FC0049.sk1.ap-south-1.eks.amazonaws.com']]) {
                sh "kubectl get pods -n webapps"
             }
            }
        }
        
    }
}
