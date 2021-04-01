pipeline {
    agent { dockerfile true }
    stages {
        stage('Cloning Git') {
            steps {
                git 'https://github.com/fr3dx/docker-webapp.git'
      }
    }
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'svn --version'
            }
        }
        stage('Push Dockerhub') {
            node {
                checkout scm
                    docker.withRegistry('https://registry.dockerhub.com', 'dockerHub') {
                    def customImage = docker.build("my-image:${env.BUILD_ID}")
        /* Push the container to the custom Registry */
        customImage.push()
                }
            }
        }
    }
}
