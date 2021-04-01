node {
        checkout scm
        docker.withRegistry('https://registry.dockerhub.com', 'dockerHub') {
        def customImage = docker.build("my-image:${env.BUILD_ID}")
        /* Push the container to the custom Registry */
        customImage.push()
        }
}

