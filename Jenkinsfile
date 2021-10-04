pipeline {
    agent {
        docker {
            image 'node:14-alpine'
            args '-p 3000:3000'
        }
    }
    stages {
        stage("Install dependeicies") {
            steps {
                git 'https://git.ceesiesdomain.nl/scm/rsd/test_automation.git'
            }
        }
    }
}
