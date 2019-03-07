#!/usr/bin/env groovy

pipeline {
    agent any

    stages {
        stage('deploy to prod') {
            steps {
                script {
                    withCredentials([file(credentialsId: env.KUBECONFIG ?: 'kubeconfig', variable: 'KUBECONFIG')]) {
                        sh 'kubectl apply --context prod-fss --namespace default -f syfoalerts.yaml'
                    }
                }
            }
        }
    }
}
