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
    }

}