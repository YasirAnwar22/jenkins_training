pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''
                echo 'Hello World'
                ls -al
                touch container-no.txt
               '''
            }
        }
        stage('w/ docker') {
            agent {
                docker {
                    image "node:18-alpine"
                    reuseNode true
                }
            }
            steps {
                echo 'Hello World Test'
                sh 'npm --version'
                   sh '''
                echo 'Hello World'
                ls -al
                touch container-yes.txt
                node start.js
               '''
            }
        }
    }
}
