pipeline {
    agent {
        docker {
            image 'node:lts-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage("Install dependeicies") {
            steps {
                sh 'npm install'
            }
        }

    }
}
