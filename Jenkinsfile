pipeline {
    agent any
    stages {
           stage('Build Image'){
                steps {
                    pwd
                    script {
                        dockerapp = docker.build("gianmilani/jenkinstest", '-f ./Dockerfile ./')
                    }
                }
           }
    }

}