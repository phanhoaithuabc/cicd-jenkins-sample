pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/phanhoaithuabc/cicd-jenkins-sample.git'
            }
        }
        stage('docker image') {
            steps {
                withDockerRegistry(credentialsId: 'jenkins-hello-workd', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t phanhoaithu/jenkins-hello-world:v1 .'
                    sh 'docker push phanhoaithu/jenkins-hello-world:v1'
                }
            }
        }
    }
}