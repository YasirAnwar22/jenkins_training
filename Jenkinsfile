pipeline {
    agent any

    stages {
        stage('Greet') {
            steps {
                echo 'Hello from Jenkins Pipeline!'
            }
        }

        stage('Build') {
            steps {
                sh '''
                  echo "Building your project..."
                  ls -la
                  node --version
                  npm --version
                  npx --version
                  npm ci
                  npm run build
                  ls -la

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
