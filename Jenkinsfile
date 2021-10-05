pipeline {
    agent {
        docker {
            image 'sitapati/docker-alpine-python-node'
            args '-p 3000:3000'
        }
    }
    environment {
        npm_config_cache='npm-cache'
    }
    stages {
        stage("Install dependeicies") {
            steps {
                sh 'npm install'
            }
        }
        stage("running") {
            steps {
                sh 'sudo chown -R $USER:$GROUP ~/.npm'
                sh 'sudo chown -R $USER:$GROUP ~/.config'
                sh 'npm start'
            }
        }
    }
}
