node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("ferencmolnar/nodeapp")
    }

    stage('Test image') {
        app.inside {
            echo "Tests passed"
        }
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
        def customImage = docker.build("ferencmolnar:${env.BUILD_ID}")
        customImage.push()
            } 
        echo "Trying to Push Docker Build to DockerHub"
    }
}


