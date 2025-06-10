pipeline {
    agent any

    tools {
        nodejs 'nodejs' // Uses the Node.js tool you configured
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out source code...'
                git branch: 'main', url: 'https://github.com/mrfaky01/My-Jenkins-Project.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies (npm install)...'
                // Running npm install directly in the repository root
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Node.js application...'
                // Running npm run start directly in the repository root
                sh 'npm run start' // This executes the 'start' script from package.json
            }
        }

        stage('Test') {
            steps {
                echo 'Running Node.js tests (npm test)...'
                // Running npm test directly in the repository root
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step placeholder. (You will add real deployment commands later)'
            }
        }
    }
}
