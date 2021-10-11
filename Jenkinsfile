pipeline {
    agent {
        docker {
            image 'mrts/docker-python-nodejs-google-chrome'
            args '-p 3000:3000'
        }
    }
    environment {
        HOME="."
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm rebuild'
            }
        }

        stage('run') {
            steps {
                sh 'npm start'
            }
        }
        
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
    }
}