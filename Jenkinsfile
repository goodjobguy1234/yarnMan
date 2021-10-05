pipeline {
    agent {
        docker {
            image 'sitapati/docker-alpine-python-node'
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
                sh 'apk add --no-cache  chromium --repository=http://dl-cdn.alpinelinux.org/alpine/v3.10/main
                sh 'npm test'
            }
        }
    }
}
