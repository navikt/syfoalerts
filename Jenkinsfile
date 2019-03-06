#!/usr/bin/env groovy

pipeline {
    agent any

    stages {
        stage('deploy to preprod') {
            steps {
                script {
                    withCredentials([file(credentialsId: env.KUBECONFIG ?: 'kubeconfig', variable: 'KUBECONFIG')]) {
                        sh 'kubectl apply --context preprod-fss --namespace default -f syfoalerts.yaml'
                    }
                }
            }
        }
    }
}
