pipeline {
    agent any

    // No 'tools' section needed since we're not using Node.js or npm locally
    // If you had other tools for static sites (like a linter), you'd put them here.

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out source code...'
                git branch: 'main', url: 'https://github.com/mrfaky01/My-Jenkins-Project.git'
            }
        }

        stage('Prepare/Build (Static)') {
            steps {
                echo 'No build step needed for simple static files. Copying/preparing...'
                // For a static site, "build" often means just copying files
                // or perhaps running a minifier/bundler if you added one later.
                sh 'cp -r ./* ./dist' // Simple copy to a 'dist' folder within workspace
            }
        }

        stage('Test (Static)') {
            steps {
                echo 'No explicit tests for this simple static site. Performing basic validation...'
                // For a static site, tests might involve:
                // - HTML validation (e.g., html-proofer)
                // - CSS linting (e.g., stylelint)
                // - JavaScript linting (e.g., ESLint, if you install Node.js on Jenkins)
                // For now, we'll just echo a success.
                sh 'echo "Static file validation placeholder completed." && exit 0'
            }
        }

        stage('Deploy (Static)') {
            steps {
                echo 'Deployment step placeholder for static website. (You will add real deployment commands here)'
                // Common deployment for static sites:
                // - Copy to an S3 bucket (AWS)
                // - Deploy to Nginx web server
                // - Push to a static hosting service (Netlify, Vercel, GitHub Pages)
                // For now, it will just pass.
            }
        }
    }

    // Optional: Add post-build actions, like cleaning up the workspace
    post {
        always {
            cleanWs() // Cleans up the workspace directory after the build
        }
    }
}