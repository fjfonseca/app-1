pipeline {
    agent {
        docker { image 'node:18.17.1-alpine3.18' }
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Unit Tests') {
            steps {
                script {
                    sh 'npm install'
                    sh 'ng test --browsers ChromeHeadless --watch=false'
                }
            }
        }

        stage('Build Angular App') {
            steps {
                script {
                    sh 'ng build --prod'
                }
            }
        }
    }
}
