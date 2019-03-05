#!/usr/bin/env groovy

pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                cleanWs()
                script {
                    withEnv(['HTTPS_PROXY=http://webproxy-internett.nav.no:8088']) {
                        withCredentials([string(credentialsId: 'OAUTH_TOKEN', variable: 'token')]) {
                            def naiseratorFile = sh(script: "curl -s https://${token}@raw.githubusercontent.com/navikt/syfoalerts/master/syfoalerts.yaml", returnStdout: true).trim()
                        }
                    }
                }
            }
        }
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
