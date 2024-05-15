pipeline {
    agent any
    stages {
           stage('Build Image'){
                steps {
                    script {
                        dockerapp = docker.build("gianmilani/jenkinstest", '-f ./src/Dockerfile ./src')
                    }
                }
           }
    }

}