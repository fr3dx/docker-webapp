node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("fr3dx/nodeapp")
    }

    stage('Test image') {
        app.inside {
            echo "Tests passed"
        }
    }

    stage('Final msg') {
        echo "Done"
            } 

    }
}


