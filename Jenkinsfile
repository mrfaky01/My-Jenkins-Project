pipeline {
    agent any // This tells Jenkins to run the pipeline on any available agent (your EC2 instance)

    tools {
        // This tells Jenkins to use the Node.js installation configured in "Manage Jenkins > Global Tool Configuration"
        // It should be named 'nodejs' and point to your /opt/nodejs installation.
        nodejs 'nodejs'
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out source code...'
                // This 'git' step checks out the code from your GitHub repository.
                // Ensure the URL is correct for your repo.
                git branch: 'main', url: 'https://github.com/mrfaky01/My-Jenkins-Project.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies (npm install)...'
                // *** IMPORTANT: Change directory into your 'node.js project' folder before running npm install ***
                sh 'cd "node.js project" && npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Node.js application (if applicable)...'
                // *** IMPORTANT: Change directory into your 'node.js project' folder before running npm run start ***
                sh 'cd "node.js project" && npm run start' // This runs the 'start' script defined in package.json
            }
        }

        stage('Test') {
            steps {
                echo 'Running Node.js tests (npm test)...'
                // *** IMPORTANT: Change directory into your 'node.js project' folder before running npm test ***
                sh 'cd "node.js project" && npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step placeholder. (You will add real deployment commands later)'
                // This stage is where you'd typically deploy your built application.
            }
        }
    }
}
