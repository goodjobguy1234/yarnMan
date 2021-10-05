pipeline {
    agent {
        docker {
            image 'sitapati/docker-alpine-python-node'
            image 'docker pull browserless/chrome'
            args '-p 3000:3000'
        }
    }
    environment {
        HOME="."
    }
    stages {
        stage("Install dependeicies") {
            steps {
                sh 'npm install'
                sh 'npm rebuild'
            }
        }
        stage("Running & Testing") {
            steps {
                sh 'npm start &'
            }
        }
        stage("Testing") {
            steps {
                sh 'npm test'
            }
        }
    }
}
