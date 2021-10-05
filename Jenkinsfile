pipeline {
    agent {
        docker {
            image 'sitapati/docker-alpine-python-node'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage("Install dependeicies") {
            steps {
                sh 'npm install'
            }
        }
        stage("running") {
            steps {
                sh 'sudo chown -R $(whoami) ~/.npm'
                sh 'sudo chown -R $(whoami) ~/.config'
                sh 'npm start'
            }
        }
    }
}
