pipeline {
    agent any // This tells Jenkins to run the pipeline on any available agent (your EC2 instance)

    tools {
        // This line tells Jenkins to find a Node.js installation configured in "Manage Jenkins > Global Tool Configuration"
        // Replace 'nodejs' with the actual name you give your Node.js tool in Jenkins, if you configure it.
        // For now, if Node.js is just manually installed on your EC2, this might not be strictly needed, but it's good practice.
        nodejs 'nodejs' // Use the name you've configured in Jenkins for your Node.js tool
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
                // Runs npm install to download and set up project dependencies
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Node.js application (if applicable)...'
                // If your Node.js project has a build step (e.g., using Webpack, Rollup, Babel),
                // you would run it here. Many modern JS apps have a 'build' script in package.json.
                // e.g., sh 'npm run build'
                // If your project doesn't have a separate build step, you can remove or comment this line.
                sh 'echo "No explicit build step configured for this example, continuing..."' // Placeholder
            }
        }

        stage('Test') {
            steps {
                echo 'Running Node.js tests (npm test)...'
                // Runs tests defined in your package.json (e.g., Jest, Mocha, Vitest)
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step placeholder. (You will add real deployment commands later)'
                // This stage is where you'd typically deploy your built application.
                // E.g., copy files to a web server, deploy to S3, publish to a container registry, etc.
            }
        }
    }
}
