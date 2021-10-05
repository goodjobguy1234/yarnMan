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
                sh 'chmod 700 chromium.sh'
                sh './chromium.sh'
                sh 'npm test'
            }
        }
    }
}
