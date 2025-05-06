pipeline {
    agent any

    stages {
        stage('Greet') {
            steps {
                echo 'Hello from Jenkins Pipeline!'
            }
        }

        stage('Build') {
            agent {
                docker {
                    image 'node:18' // Use full Debian-based Node instead of Alpine
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "Node.js Build Stage"
                    node -v
                    npm -v

                    rm -rf node_modules
                    npm cache clean --force

                    npm install
                    npm run build
                '''
            }
}

        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying application..."'
            }
        }
    }
}
