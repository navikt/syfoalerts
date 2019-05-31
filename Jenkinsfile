#!/usr/bin/env groovy

pipeline {
    agent any

    stages {
        stage('deploy to prod-fss') {
            steps {
                script {
                    withCredentials([file(credentialsId: env.KUBECONFIG ?: 'kubeconfig', variable: 'KUBECONFIG')]) {
                        sh 'kubectl --context prod-fss --namespace default delete alert syfoalerts'
                        sh 'kubectl apply --context prod-fss --namespace default -f syfoalerts.yaml'
                    }
                }
            }
        }
        stage('deploy to prod-sbs') {
            steps {
                script {
                    withCredentials([file(credentialsId: env.KUBECONFIG ?: 'kubeconfig', variable: 'KUBECONFIG')]) {
                        sh 'kubectl --context prod-sbs --namespace default delete alert syfoalerts-sbs'
                        sh 'kubectl apply --context prod-sbs --namespace default -f syfoalerts-sbs.yaml'
                    }
                }
            }
        }
        stage('cleanup') {
            steps {
                cleanWs()
            }
        }
    }
}
