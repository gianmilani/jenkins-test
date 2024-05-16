pipeline {
    agent any
    stages {
           stage('Build Image'){
                steps {
                    script {
                        dockerapp = docker.build("gianmilani/jenkinstest:${env.BUILD_ID}", '-f ./Dockerfile ./')
                    }
                }
           }
           stage('Push image'){
                steps {
                    script {
                        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                            dockerapp.push('latest')
                            dockerapp.push("${env.BUILD_ID}")
                        }
                    }
                }
           }
           stage('Deploy Kubernetes'){
                steps {
                    withKubeConfig([credentialsId: 'kubeconfig']){
                        sh 'kubectl apply -f ./k8s/deployment.yaml'
                    }
                }
           }
    }

}